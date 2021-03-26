# physarium-dataset

Code for creating the [Physarium Latent Walk Dataset](https://www.kaggle.com/).

## Recreation

Install physarum util (TODO:link). Then I created 1000 images with random settings and logged them in random.log with physarum-util like this:

```bash
cd physarum-util
go run main.go -size 1024 -path random/random_%d.png --logPath "random.log"
```

I selected a few images for the dataset and created 100 images with the same settings pointing to the log file with the image path and zipped them like this:

```bash
go run main.go -path <name>/<name>_%d.png --configLogPath "random.log" --configsLike "<path-to-image-from-random>" -numOfExamples 100
zip <name> <name>/*
```

Here are all the commands for generating the images in the [Physarium Latent Walk Dataset](https://www.kaggle.com/):

```bash
# cells
go run main.go -path cells/cells_%d.png --configLogPath "random.log" --configsLike "random/random_134836929.png" -numOfExamples 100
zip cells cells/*

# colorful_cells
go run main.go -path colorful_cells/colorful_cells_%d.png --configLogPath "random.log" --configsLike "random/random_134839255.png" -numOfExamples 100
zip colorful_cells colorful_cells/*

# duckwheat
go run main.go -path duckwheat/duckwheat_%d.png --configLogPath "random.log" --configsLike "random/random_133287917.png" -numOfExamples 100
zip duckwheat duckwheat/*

# dunes
go run main.go -path dunes/dunes_%d.png --configLogPath "random.log" --configsLike "random/random_133514569.png" -numOfExamples 100
zip dunes dunes/*

# fire
go run main.go -path fire/fire_%d.png --configLogPath "random.log" --configsLike "random/random_133351589.png" -numOfExamples 100
zip fire fire/*

# giraffe
go run main.go -path giraffe/giraffe_%d.png --configLogPath "random.log" --configsLike "random/random_134290509.png" -numOfExamples 100
zip giraffe giraffe/*

# grid
go run main.go -path grid/grid_%d.png --configLogPath "random.log" --configsLike "random/random_133890901.png" -numOfExamples 100
zip grid grid/*

# labyrinth
go run main.go -path labyrinth/labyrinth_%d.png --configLogPath "random.log" --configsLike "random/random_133416078.png" -numOfExamples 100
zip labyrinth labyrinth/*

# layer
go run main.go -path layer/layer_%d.png --configLogPath "random.log" --configsLike "random/random_134668451.png" -numOfExamples 100
zip layer layer/*

# plant_cells
go run main.go -path plant_cells/plant_cells_%d.png --configLogPath "random.log" --configsLike "random/random_133817618.png" -numOfExamples 100
zip plant_cells plant_cells/*

# red_flow
go run main.go -path red_flow/red_flow_%d.png --configLogPath "random.log" --configsLike "random/random_133253768.png" -numOfExamples 100
zip red_flow red_flow/*

# runes
go run main.go -path runes/runes_%d.png --configLogPath "random.log" --configsLike "random/random_133419888.png" -numOfExamples 100
zip runes runes/*

# space1
go run main.go -path space1/space1_%d.png --configLogPath "random.log" --configsLike "random/random_133795889.png" -numOfExamples 100
zip space1 space1/*

# space2
go run main.go -path space2/space2_%d.png --configLogPath "random.log" --configsLike "random/random_134138416.png" -numOfExamples 100
zip space2 space2/*

# sponge
go run main.go -path sponge/sponge_%d.png --configLogPath "random.log" --configsLike "random/random_134807196.png" -numOfExamples 100
zip sponge sponge/*

# thunder
go run main.go -path thunder/thunder_%d.png --configLogPath "random.log" --configsLike "random/random_133609260.png" -numOfExamples 100
zip thunder thunder/*

# universe
go run main.go -path universe/universe_%d.png --configLogPath "random.log" --configsLike "random/random_134761447.png" -numOfExamples 100
zip universe universe/*

# vines
go run main.go -path vines/vines_%d.png --configLogPath "random.log" --configsLike "random/random_133857414.png" -numOfExamples 100
zip vines vines/*

# wetlands
go run main.go -path wetlands/wetlands_%d.png --configLogPath "random.log" --configsLike "random/random_134282193.png" -numOfExamples 100
zip wetlands wetlands/*
```

## Util

Throttle the cpu usage of the highest process to e.g. 220% for Linux.

```bash
# installation with ubuntu:
sudo apt-get install cpulimit

cpulimit -p $(ps ahux --sort=-c | awk 'NR<=1{printf"%6d\n",$2}') -l 220
```