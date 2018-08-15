# Basic payment
//This is the first PHP code, intended as an application for basic payments, includes a 4-steps algorithm for tests of PSE (saving and //current accounts).

<?php

# Seleccion del banco: cliente y banco

//Variable type sring
$ClientType = "persona";
echo "El tipo de cliente es: $ClientType<br>";
var_dump($ClientType);
echo "<br><br>";

//Variable type array
$ListaBancos = array("Seleccione uno","Banco GNB Colombia","Banco MAPG");
echo "Estos son los bancos disponibles en el dia de hoy<br>";
var_dump($ListaBancos);
echo "<br><br>";

?>
