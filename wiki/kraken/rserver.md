## Pull singularity rserver docker

Note latest does not work 
```bash
cd
mkdir singularity-images; 
cd singularity-images
module load singularity
# singularity pull --name rstudio.simg docker://rocker/tidyverse:latest
singularity pull --name rstudio.simg docker://rocker/tidyverse:3.6.3
# singularity exec rstudio.simg rserver --www-address=127.0.0.1
PASSWORD='asdf' singularity exec --bind=/liulab/asahu  rstudio.simg rserver --auth-none=0  --auth-pam-helper-path=pam-helper  --www-address=127.0.0.1
```

## SSH tuneling
```bash
ssh -f -L 59083:localhost:59083 $KRAKEN ssh -L 59083:localhost:8787 -N node16
# ssh -Y -L 51812:localhost:51812 $KRAKEN
```

Login @ localhost:59083