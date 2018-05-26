# GeoFindKey
Conformal transformation

Conformal transformation on the plane is widely used in geodesy when creating local coordinate systems in small areas, limited by the size of the settlement.

## DOCUMENTATION

See doc/*

## BUILD

The procedure for compiling is:

    cd src
    make

## SAMPLE

GeoFindKey:

Input Data ../doc/data.dat:

    1 1334.71   285.94 66.29 83477.64 47377.60 216.28 1.0
    2  563.67 -5197.34 60.21 82557.14 41916.51 210.21 1.0
    3 4444.27  1153.79 67.76 86610.19 48160.39 217.77 1.0
    4 -252.07  2881.90 65.41 81962.05 50016.34 215.42 1.0
    5 1334.71   285.94 66.29
    6  563.67 -5197.34 60.21
    7 4444.27  1153.79 67.76
    8 -252.07  2881.90 65.41

Mode Normal:

    ./geofindkey ../doc/data.dat report.dat

Result report.dat:

    key:
    82135.4073
    47128.1437
    150.0025
    0.999787994227
    -0.027289778074
    1.000531067446
    1.000160369835
    -1.5635324426
    
    var:
    (Mode Normal)
    1 1334.7100 285.9400 66.2900 83477.6400 47377.6000 216.2800 1 +0.0024 +0.0008 -0.0132 -0.0002735462 -0.0000
    2 563.6700 -5197.3400 60.2100 82557.1400 41916.5100 210.2100 1 +0.0165 -0.0132 +0.0000 +0.0002137624 +0.0093
    3 4444.2700 1153.7900 67.7600 86610.1900 48160.3900 217.7700 1 -0.0318 -0.0160 +0.0060 -0.0000341993 -0.0355
    4 -252.0700 2881.9000 65.4100 81962.0500 50016.3400 215.4200 1 +0.0129 +0.0283 +0.0072 -0.0003963128 +0.0189
    5 1334.7100 285.9400 66.2900 83477.6376 47377.5992 216.2932
    6 563.6700 -5197.3400 60.2100 82557.1235 41916.5232 210.2100
    7 4444.2700 1153.7900 67.7600 86610.2218 48160.4060 217.7640
    8 -252.0700 2881.9000 65.4100 81962.0371 50016.3117 215.4128
    
    diff:
    0.0269 0.0248 0.0115 0.0003672639 0.0292

Mode Rescale:

    ./geofindkey -r ../doc/data.dat report.dat

Result report.dat:

    key:
    82135.4073
    47128.1437
    150.0025
    0.999787994227
    -0.027289778074
    1.000531067446
    1.000160369835
    -1.5635324426
    
    var:
    (Mode Rescale)
    1 1334.7100 285.9400 66.2900 83477.6400 47377.6000 216.2800 1 -0.0255 +0.0826 -0.0125 -0.0002735462 +0.0864
    2 563.6700 -5197.3400 60.2100 82557.1400 41916.5100 210.2100 1 -0.1591 -0.8071 -0.0025 +0.0002137624 +0.8224
    3 4444.2700 1153.7900 67.7600 86610.1900 48160.3900 217.7700 1 +0.4426 +0.1913 +0.0075 -0.0000341993 +0.4822
    4 -252.0700 2881.9000 65.4100 81962.0500 50016.3400 215.4200 1 -0.2581 +0.5332 +0.0075 -0.0003963128 +0.5918
    5 1334.7100 285.9400 66.2900 83477.6655 47377.5174 216.2925
    6 563.6700 -5197.3400 60.2100 82557.2991 41917.3171 210.2125
    7 4444.2700 1153.7900 67.7600 86609.7474 48160.1987 217.7625
    8 -252.0700 2881.9000 65.4100 81962.3081 50015.8068 215.4125
    
    diff:
    0.3798 0.6997 0.0117 0.0003672639 0.7958

Mode Station Rescale:

    ./geofindkey -r -s ../doc/data.dat report.dat

Result report.dat:

    key:
    82135.4073
    47128.1437
    150.0025
    0.999787994227
    -0.027289778074
    1.000531067446
    1.000160369835
    -1.5635324426
    
    var:
    (Mode Station Rescale)
    1 1334.7100 285.9400 66.2900 83477.6400 47377.6000 216.2800 1 +0.2177 +0.0408 -0.0125 +0.0000155927 +0.2214
    2 563.6700 -5197.3400 60.2100 82557.1400 41916.5100 210.2100 1 +0.0841 -0.8488 -0.0025 +0.0001681880 +0.8528
    3 4444.2700 1153.7900 67.7600 86610.1900 48160.3900 217.7700 1 +0.6858 +0.1495 +0.0075 -0.0001051948 +0.7018
    4 -252.0700 2881.9000 65.4100 81962.0500 50016.3400 215.4200 1 -0.0149 +0.4914 +0.0075 -0.0002877147 +0.4914
    5 1334.7100 285.9400 66.2900 83477.4223 47377.5592 216.2925
    6 563.6700 -5197.3400 60.2100 82557.0559 41917.3588 210.2125
    7 4444.2700 1153.7900 67.7600 86609.5042 48160.2405 217.7625
    8 -252.0700 2881.9000 65.4100 81962.0649 50015.8486 215.4125
    
    diff:
    0.5123 0.7021 0.0117 0.0002495968 0.8690

S-Z-B to Y-X-H conert:

Input Data ../doc/szb.dat:

    OKD-4     8.605  74.08666667   234.38916667  7471.2970  14588.7117  98.7445
    OKD-5     8.869  81.18888889   254.73888889  7474.2548  14589.4514  97.7433
    OKD-K3-1  3.670  82.43944444   339.05361111  7477.0949  14580.7517  96.8713
    OKD-K3-4  3.690  70.66833333   161.16        7469.9723  14580.8231  97.6075
    OKD-K5P   3.938  71.95527778   137.52222222  7469.9811  14579.3211  97.6057
    OKD-K7L   4.685  83.96444444   17.82444444   7477.1099  14577.8330  96.8789
    OKD-K7L   4.684  276.03361111  197.82722222  7477.1099  14577.8330  96.8789
    OKD-K5P   3.939  288.04361111  317.52472222  7469.9811  14579.3211  97.6057
    OKD-K3-4  3.691  289.32972222  341.16111111  7469.9723  14580.8231  97.6075
    OKD-K3-1  3.671  277.55583333  159.05805556  7477.0949  14580.7517  96.8713
    OKD-5     8.869  278.80944444  74.74055556   7474.2548  14589.4514  97.7433
    OKD-4     8.604  285.91444444  54.38972222   7471.2970  14588.7117  98.7445
    OKD-11    3.889  71.6025       313.60777778
    OKD-12    3.889  288.39138889  133.60805556

Exec convert:

    ./geoszbtoyxh ../doc/szb.dat yxh.dat

Result yxh.dat:

    OKD-4 -6.7277 -4.8185 2.3593 7471.2970 14588.7117 98.7445 1
    OKD-5 -8.4553 -2.3069 1.3585 7474.2548 14589.4514 97.7433 1
    OKD-K3-1 -1.3006 3.3977 0.4829 7477.0949 14580.7517 96.8713 1
    OKD-K3-4 1.1244 -3.2954 1.2215 7469.9723 14580.8231 97.6075 1
    OKD-K5P 2.5285 -2.7616 1.2198 7469.9811 14579.3211 97.6057 1
    OKD-K7L 1.4261 4.4354 0.4926 7477.1099 14577.8330 96.8789 1
    OKD-K7L 1.4261 4.4344 0.4923 7477.1099 14577.8330 96.8789 1
    OKD-K5P 2.5291 -2.7624 1.2201 7469.9811 14579.3211 97.6057 1
    OKD-K3-4 1.1247 -3.2964 1.2217 7469.9723 14580.8231 97.6075 1
    OKD-K3-1 -1.3007 3.3987 0.4827 7477.0949 14580.7517 96.8713 1
    OKD-5 -8.4554 -2.3067 1.3583 7474.2548 14589.4514 97.7433 1
    OKD-4 -6.7269 -4.8178 2.3592 7471.2970 14588.7117 98.7445 1
    OKD-11 -2.6720 2.5452 1.2274
    OKD-12 -2.6721 2.5453 1.2270

SIter (estimation of unknown distances):

Input Data ../doc/szbunknow.dat:

    OKD-4     -1     74.08666667   234.38916667  7471.2970  14588.7117  98.7445
    OKD-5     -1     81.18888889   254.73888889  7474.2548  14589.4514  97.7433
    OKD-K3-1  -1     82.43944444   339.05361111  7477.0949  14580.7517  96.8713
    OKD-K3-4  -1     70.66833333   161.16        7469.9723  14580.8231  97.6075
    OKD-K5P   -1     71.95527778   137.52222222  7469.9811  14579.3211  97.6057
    OKD-K7L   -1     83.96444444   17.82444444   7477.1099  14577.8330  96.8789
    OKD-K7L   -1     276.03361111  197.82722222  7477.1099  14577.8330  96.8789
    OKD-K5P   -1     288.04361111  317.52472222  7469.9811  14579.3211  97.6057
    OKD-K3-4  -1     289.32972222  341.16111111  7469.9723  14580.8231  97.6075
    OKD-K3-1  -1     277.55583333  159.05805556  7477.0949  14580.7517  96.8713
    OKD-5     -1     278.80944444  74.74055556   7474.2548  14589.4514  97.7433
    OKD-4     -1     285.91444444  54.38972222   7471.2970  14588.7117  98.7445
    OKD-11    3.889  71.6025       313.60777778
    OKD-12    3.889  288.39138889  133.60805556

Exec convert:

    ./geositer500 ../doc/szbunknow.dat szb.dat

Result sbz.dat:

    OKD-4 8.6045 74.08666667 234.38916667 7471.2970 14588.7117 98.7445
    OKD-5 8.8697 81.18888889 254.73888889 7474.2548 14589.4514 97.7433
    OKD-K3-1 3.6731 82.43944444 339.05361111 7477.0949 14580.7517 96.8713
    OKD-K3-4 3.6912 70.66833333 161.16000000 7469.9723 14580.8231 97.6075
    OKD-K5P 3.9388 71.95527778 137.52222222 7469.9811 14579.3211 97.6057
    OKD-K7L 4.6861 83.96444444 17.82444444 7477.1099 14577.8330 96.8789
    OKD-K7L 4.6861 276.03361111 197.82722222 7477.1099 14577.8330 96.8789
    OKD-K5P 3.9388 288.04361111 317.52472222 7469.9811 14579.3211 97.6057
    OKD-K3-4 3.6912 289.32972222 341.16111111 7469.9723 14580.8231 97.6075
    OKD-K3-1 3.6731 277.55583333 159.05805556 7477.0949 14580.7517 96.8713
    OKD-5 8.8697 278.80944444 74.74055556 7474.2548 14589.4514 97.7433
    OKD-4 8.6045 285.91444444 54.38972222 7471.2970 14588.7117 98.7445
    OKD-11 3.8890 71.60250000 313.60777778
    OKD-12 3.8890 288.39138889 133.60805556

https://github.com/zvezdochiot/geofindkey
