#SMS OTP Form
SMS OTP (One time password) form
```
<form>
  <input
    type="text"
    inputmode="numeric"
    autocomplete="one-time-code"
    pattern="\d{6}"
  </input>
...
</form>
```

Format message for safari and chrome
```
blabla bla your otp is: 213412

@lichfolky.com #213412
```
the last line it's recognised automatically by safari
with chrome you should use a web OTP api:

```
if ('OTPcredential' in window){
  const input = document.queryselector('input[autocomplete="one-time-code"]');
  if('input'){
    // this is the web OTP api:
    navigator.credential.get(
      {otp:{transport:['sms']}
    }).then(otp => input.value=otp.code);
  }
}
```
the browser will start to wait for an SMS with that format

check
- web.dev/sms-otp-form
- web.dev/web-otp
