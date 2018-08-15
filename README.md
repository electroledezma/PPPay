# Basic payment
// This is the first PHP code, intended as an application for basic payments, includes a 4-steps algorithm for tests of PSE (saving and current accounts).

<?php

# Asking for client (cliente) and bank (banco)

//Variable type sring
$ClientType = "persona";
echo "The type of client is: $ClientType<br>";
var_dump($ClientType);
echo "<br><br>";

//Variable type array
$BankList = array("Select one","Banco GNB Colombia","Banco MAPG");
echo "These are the banks available for today<br>";
var_dump($BankList);
echo "<br><br>";

////////////////////////////////////////////////////////////////////////////

Test of banks:
  32bit:
    docker:
      - image: quay.io/pypa/manylinux1_i686
    steps:
      - checkout
      - run:
          name: Install dependencies
          command: /opt/python/cp36-cp36m/bin/pip install numpy scipy "pytest<3.7" pytest-astropy pytest-xdist Cython jinja2
      - run:
          name: Run tests
          command: PYTHONHASHSEED=42 /opt/python/cp36-cp36m/bin/python setup.py test --parallel=4
  image-tests-mpl202:
    docker:
      - image: astropy/image-tests-py35-mpl202:1.2
    steps:
      - checkout
      - run:
          name: Run tests
          command: |
            python3 setup.py test -P visualization --remote-data=astropy -a "--mpl"
  image-tests-mpl212:
    docker:
      - image: astropy/image-tests-py35-mpl212:1.2
    steps:
      - checkout
      - run:
          name: Run tests
          command: |
            python3 setup.py test -P visualization --remote-data=astropy -a "--mpl"
            
////////////////////////////////////////////////////////////////////////////


?>
