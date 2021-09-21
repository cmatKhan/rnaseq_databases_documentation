## ZEV_induction

The goal of this experiment is to determine the number of deferentially expressed genes when an engineered strain is induced following the flooding of the plate 30 minutes prior to induction with SC+2% galactose media (used to resuspend cells growing on an agarose plate). This experiment is the standard protocol for the ZEV induction project as of 11/2019 and will be used on all strains such as CBF1, TYE7, GCN4, RGT1, and so on.  

The basic procedure is to grow cells on agarose plates with synthetic complete medium plus 2% galactose (SCGal), resuspend cells by flooding the plates with a liquid and resuspending with a loop, add an estradiol dissolved in ethanol or just the ethanol (mock inducer), and take samples for RNA-Seq just before and at time points after the inducer or mock inducer has been added.

The fields needed to differentiate all the samples are

__floodMedia__ -- the fluid used to resuspend cells growing on plates. One of:
    • SCGal

__inductionDelay__ -- the time between resuspension of cells and addition of inducer or mock inducer.

    • 30 -- inducer or mock inducer added 30 minutes after cells are resuspended

__treatment__ -- the inducer or mock inducer added. One of:
    • Estradiol -- the ZEV inducer, dissolved in ethanol
    • EtOH -- ethanol only, equal volume to the true induction

__timePoint__ -- the time between addition of the inducer or mock inducer and cell harvesting. Not all of the following time points may be used in a single experiment. Choose from one of:
    • -1 -- cells harvested 1 minute before addition of inducer or mock inducer
    • 10 -- cells harvested 10 minutes after addition of inducer or mock inducer
    • 15 -- cells harvested 15 minutes after addition of inducer or mock inducer
    • 20 -- cells harvested 20 minute before addition of inducer or mock inducer
    • 30 -- cells harvested 30 minutes after addition of inducer or mock inducer
    • 45 -- cells harvested 45 minutes after addition of inducer or mock inducer
    • 90 -- cells harvested 90 minutes after addition of inducer or mock inducer


Details of the experiment design