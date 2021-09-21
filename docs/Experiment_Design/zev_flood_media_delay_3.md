## ZEV_flood_media_delay_3

The goal of this experiment is to determine which of two timing (15 & 30 minutes) options results in the fewest gene expression changes in WT BY4741 cells when flooding the plates with SC+2% galactose media (used to resuspend cells growing on an agarose plate).

The basic procedure is to grow cells on agarose plates with synthetic complete medium plus 2% galactose (SCGal), resuspend cells by flooding the plates with a liquid and resuspending with a loop, add an estradiol dissolved in ethanol or just the ethanol (mock inducer), and take samples for RNA-Seq just before and at time points after the inducer or mock inducer has been added.

The fields needed to differentiate all the samples are

floodMedia -- the fluid used to resuspend cells growing on plates. One of:
    • SCGal

inductionDelay -- the time between resuspension of cells and addition of inducer or mock inducer.

    • 30 -- inducer or mock inducer added 30 minutes after cells are resuspended
    • 15 -- inducer or mock inducer added 15 minutes after cells are resuspended

treatment -- the inducer or mock inducer added. One of:
    • Estradiol -- the ZEV inducer, dissolved in ethanol
    • EtOH -- ethanol only, equal volume to the true induction

timePoint -- the time between addition of the inducer or mock inducer and cell harvesting. One of:
    • -1 -- cells harvested 1 minute before addition of inducer or mock inducer
    • 15 -- cells harvested 15 minutes after addition of inducer or mock inducer

Details of the experiment design

