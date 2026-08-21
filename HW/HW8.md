This is an ungraded homework to make Session 9 in-class activity quicker.  

Log into MSU HPCC via OnDemand. 
Go to a development node and enter an interactive session. 
Run the following to install tidyverse packages in your R environment. 
You can copy and paste line by line to run them. 

```
ml purge 
ml R/4.3.2-gfbf-2023a-ICER # Make sure you load the right version from HPCC  
R 
install.packages("tidyverse")  
```

It may take 30 min or more to install everything.  
When installing packages, choose CRAN mirror 1 or 64 when prompted. 
You only need to install packages once.  
When it is done installing, the prompt will be active again (showing ">"). 

To validate everything is correctly installed, 
run: 

```
library(tidyverse) # Loads tidyverse packages
dim(starwars)
```

It should show `[1] 87 14`. 
You can now close your terminal window. 
