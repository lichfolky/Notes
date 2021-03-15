```
brew install php@8.0

...

To enable PHP in Apache add the following to httpd.conf and restart Apache:
    LoadModule php_module /usr/local/opt/php/lib/httpd/modules/libphp.so

    <FilesMatch \.php$>
        SetHandler application/x-httpd-php
    </FilesMatch>

Finally, check DirectoryIndex includes index.php
    DirectoryIndex index.php index.html

The php.ini and php-fpm.ini file can be found in:
    /usr/local/etc/php/8.0/

To have launchd start php now and restart at login:
  brew services start php
Or, if you don't want/need a background service you can just run:
  php-fpm

```




<?php
function getAllFoos($db) {
    return $db->query('SELECT * FROM tabella');
}

foreach (getAllFoos($db) as $row) {
    echo "<li>".$row['campo1']." - ".$row['campo2']."</li>";
}

<?php
    $pdo = new PDO('sqlite:/path/db/utenti.db');
    $stmt = $pdo->prepare('SELECT nome FROM utenti WHERE id = :id');
    $id = filter_input(INPUT_GET, 'id', FILTER_SANITIZE_NUMBER_INT); // <-- filtra prima i tuoi dati (vedi [Filtraggio dei dati](#data_filtering)), in particolare per operazioni INSERT, UPDATE etc.
    $stmt->bindParam(':id', $id, PDO::PARAM_INT); // <-- Pulito automaticamente da PDO
    $stmt->execute();
?php>


ciao