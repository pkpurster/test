<?php

if (isset($_POST["verzenden"])) {

    $voornaam = $_POST["voornaam"];
    $achternaam = $_POST["achternaam"];
    $adres = $_POST["adres"];
    $postcode = $_POST["postcode"];
    $woonplaats = $_POST["woonplaats"];
    $bsn = $_POST["bsn"];
    $geboortedatum = $_POST["geboortedatum"];

    $connection = mysqli_connect('localhost', 'root', '', 'bronnen');

    if ($connection) {
        echo "we are connected";
    } else {
        die("database connection failed");
    };

    $query = "INSER INTO bronnen(voornaam, achternaam,adres,postcode,woonplaats,bsn,geboortedatum)";
    $query .= "VALUES ('$voornaam','$achternaam', '$adres', '$postcode', '$woonplaats', '$bsn' , '$geboortedatum')";


    $result = mysqli_query($connection, $query);
};
