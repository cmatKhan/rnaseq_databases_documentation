## ZEV_scgal_media_comparison

The goal of this experiment is to determine which flooding media (SC galactose, SC glucose, PBS; used to resuspend cells growing on an agarose plate) produces the best results for gene expression changes when inducing the McIsaac transcription factor strains. Plates were flooded 15 minutes prior to induction occurring. CBF1 cells were induced in this experiment.  

The basic procedure is to grow cells on agarose plates with either synthetic complete medium plus 2% galactose (SCGal) or 2% glucose (SCGlu), or PBS, and resuspend cells by flooding the plates with a liquid and resuspending with a spreader, add an estradiol dissolved in ethanol or just the ethanol (mock inducer), and take samples for RNA-Seq just before and at time points after the inducer or mock inducer has been added.

The fields needed to differentiate all the samples are

__floodMedia__ -- the fluid used to resuspend cells growing on plates. One of:
    • SCGal
    • SCGlu
    • PBS

__inductionDelay__ -- the time between resuspension of cells and addition of inducer or mock inducer.

    • 15 -- inducer or mock inducer added 15 minutes after cells are resuspended

__treatment__ -- the inducer or mock inducer added. One of:
    • Estradiol -- the ZEV inducer, dissolved in ethanol
    • EtOH -- ethanol only, equal volume to the true induction

__timePoint__ -- the time between addition of the inducer or mock inducer and cell harvesting. One of:
    • -1 -- cells harvested 1 minute before addition of inducer or mock inducer
    • 15 -- cells harvested 15 minutes after addition of inducer or mock inducer
    • 90 -- cells harvested 90 minutes after addition of inducer or mock inducer


Details of the experiment design
