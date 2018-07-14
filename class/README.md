<!-- README.md --- 
;; 
;; Description: 
;; Author: Hongyi Wu(吴鸿毅)
;; Email: wuhongyi@qq.com 
;; Created: 四 7月 12 07:58:03 2018 (+0800)
;; Last-Updated: 六 7月 14 05:10:53 2018 (+0800)
;;           By: Hongyi Wu(吴鸿毅)
;;     Update #: 3
;; URL: http://wuhongyi.cn -->

# README


## EM

```cpp
        "gamma",            "e-",           "e+",           "mu+",        "mu-",
          "pi+",           "pi-",        "kaon+",         "kaon-",     "proton",
  "anti_proton",         "alpha",          "He3",    "GenericIon",         "B+",
           "B-",            "D+",           "D-",           "Ds+",        "Ds-",
     "anti_He3",    "anti_alpha","anti_deuteron","anti_lambda_c+","anti_omega-",
"anti_sigma_c+","anti_sigma_c++",  "anti_sigma+",   "anti_sigma-","anti_triton",
   "anti_xi_c+",      "anti_xi-",     "deuteron",     "lambda_c+",     "omega-",
     "sigma_c+",     "sigma_c++",       "sigma+",        "sigma-",       "tau+",
         "tau-",        "triton",        "xi_c+",           "xi-"
```


```cpp
enum G4EmTableType
{
  fTotal = 0,
  fRestricted,
  fSubRestricted,
  fIsIonisation,
  fIsSubIonisation,
  fIsCrossSectionPrim
};
```


<!-- README.md ends here -->