# mat-twitter-score-analyzer
The visualization of affinity data from [mat-twitter-downloader](https://github.com/zabkwak/mat-twitter-downloader). It's based on shiny app.

## Development
### Requirements
- R (Rscript)
#### Ubuntu
- libglu1
- libxml2
- libbglpk-dev

### Installation & test run
```bash
git clone git@github.com:zabkwak/mat-twitter-score-analyzer.git
cd mat-twitter-score-analyzer
Rscript -e "install.packages(c('shiny', 'shinythemes', 'ade4', 'vegan', 'vegan3d', 'polycor', 'psych', 'BayesLCA', 'igraph))"
Rscript main.R
```
The app will be accessible on `http://localhost:8080`.

### Dockerfile
Make sure all new packages are installed in `Dockerfile` with `RUN install2.r --error [package]`.

## Settings
No additional configuration is needed.

## Docker
The [image](https://github.com/zabkwak/mat-twitter-score-analyzer/pkgs/container/mat-twitter-score-analyzer) is stored in GitHub packages registry and the app can be run in the docker environment.
```bash
docker pull ghcr.io/zabkwak/mat-twitter-score-analyzer:latest
```

```bash
docker run \
-p 8080:8080 \
-d \
--restart=unless-stopped \
--name=mat-twitter-score-analyzer \
ghcr.io/zabkwak/mat-twitter-score-analyzer:latest  
```
The app will be accessible on `http://localhost:8080`.
