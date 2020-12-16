netstat -nlp | grep 4200
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
tcp        0      0 127.0.0.1:4200          0.0.0.0:*               LISTEN      5449/ng
agilelab@agilelab-mattia:~/Coding/Agile.Insurance.Backoffice/ui3$ kill -9 5449
agilelab@agilelab-mattia:~/Coding/Agile.Insurance.Backoffice/ui3$ npm start
