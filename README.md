# Daphnia

To obtain inference results from the data (Daphnia_LTE_master_20171013.csv), run the code Test_Compact.R and the functions present in the file FUNCTIONS_CODE.R

###############################################################################################################################################################
the input can be passed via terminal and corrrespond to the MACROS 

#####################################################################
to select clone, treatment and priors settings:

TREAT_TEST   to select the treatment (dz = Insecticide Diazon used for publication, dr = Herbicide Diuron, dr_dz = both pesticed and herbicide, Cont = Control)
CLONE_TEST   to select the clone (D2 used for publication. others are D1, D3, Ds)
PRIORS       to select priors Priors <- 1 informative; PRIORS <- 2 unifiormative

#####################################################################
and to select the model version to fit to the data:

FECUNDITY      to select fertility distribution     (P for Poisson or N for negative binomial)
ZERO_INFLATION to selectZero inflation              (TURE or FALSE)
TIME_DEP       to select time dependent mortality   (TRUE or FALSE)
CROWDING       to select desity dependent moratlity (TRUE or FALSE)
INF_METH       to select model application strategy (J for joint calibration, 
                                                     R for replica by replica calibration, and 
                                                     H for hierarchical calibration).

#####################################################################
Other MACROS present in the code are:

GET_REAL_DATA   this is to obtain the data from the file (it has to be always T)
PLOT_REAL_DATA  if TRUE plots the data (and to transforms them in a suitable format)

#####################################################################
MACROS for inference inference

INFERENCE   <- T  This selects the part of code which produces the JAGS code to perform inference
                  and the corresponding JAGS outputs (parmeters chains and historgrams)

Other MACROS to otimize inference are
INITIALIZE_CHAINS      (if TRUE creates a test chain to then initialize the inference)
INTERPOLATE            (if TRUE produces interpolated initila conditions for the states of the model)
MAKE_CONSISTENT        (if TRUE checks for inconsitencies in the initial conditions)
COMPUTE_DIC            (if TRUE uses built in functions to compute DIC)
PLOT_CORR              (if TRUE plots also 2d marginals )                                                    

#####################################################################
MACROS for plottig of model predictions

CHECK_CHAIN <- T 

other MACROS for the plotting are
PLOT_SHADE    (if TRUE) plotting only forward simulated model parameters for one replica
PLOT_SHADE_2  (if TRUE) plotting both forward simulated model parameters and states for one replica
PLOT_SHADE_3  (if TRUE) plotting both forward simulated model parameters, hyperparameters and states  for one replica (only for hierarchical models)

PLOT_ALL      (if TRUE) plotting all the data and model predictions and (only joint fit) 

###############################################################################################################################################################
The code is well commented and once the above macros are fixed inference is performed and the output file with the results for a specific model version is produced.

                                                     
