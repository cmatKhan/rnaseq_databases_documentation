## ZEV_induction_30min_delay

The goal of this experiment is to determine how induction performs on the McIsaac ZEV strains under a 30 minute flooding time when flooding plates with SC+2% galactose media (used to resuspend cells growing on an agarose plate). For this experiment we are testing induction on the CBF1 strain. 

The basic procedure is to grow cells on agarose plates with synthetic complete medium plus 2% galactose (SCGal), resuspend cells by flooding the plates with a liquid and resuspending with a loop, add an estradiol dissolved in ethanol or just the ethanol (mock inducer), and take samples for RNA-Seq just before and at time points after the inducer or mock inducer has been added.

The fields needed to differentiate all the samples are

floodMedia -- the fluid used to resuspend cells growing on plates. One of:
    • SCGal

inductionDelay -- the time between resuspension of cells and addition of inducer or mock inducer.

    • 30 -- inducer or mock inducer added 30 minutes after cells are resuspended

treatment -- the inducer or mock inducer added. One of:
    • Estradiol -- the ZEV inducer, dissolved in ethanol
    • EtOH -- ethanol only, equal volume to the true induction

timePoint -- the time between addition of the inducer or mock inducer and cell harvesting. One of:
    • -1 -- cells harvested 1 minute before addition of inducer or mock inducer
    • 15 -- cells harvested 15 minutes after addition of inducer or mock inducer
    • 90 -- cells harvested 90 minutes after addition of inducer or mock inducer


Details of the experiment design
