# Dockerized Software for [ValueEval'23](https://touche.webis.de/semeval23/touche23-web/index.html)
[TIRA page](https://www.tira.io/task/valueeval-at-semeval-2023-human-value-detection)

<p id="instructions">Place one <code>arguments.tsv</code> from the <a href="https://doi.org/10.5281/zenodo.6814563">dataset</a> in a directory <code>input</code>. For example:</p>

```
mkdir input
wget https://zenodo.org/record/7550385/files/arguments-test.tsv -O input/arguments.tsv
```

<p>Then run the software as described below to produce results in the directory <code>output</code> (requires <a href="https://docs.docker.com/engine/installation/">Docker</a>).</p>

## List of software
- [Team `aristotle`](#team-aristotle)
  - [Software `1-baseline`](#software-1-baseline)
  - [Software `BERT cuda`](#software-bert-cuda)
  - [Software `BERT nocuda`](#software-bert-nocuda)
  - [Software `Random baseline`](#software-random-baseline)
  - [Software `SVM`](#software-svm)
- [Team `augustine-of-hippo`](#team-augustine-of-hippo)
  - [Software `augustine`](#software-augustine)
  - [Software `mixture-augustine`](#software-mixture-augustine)
  - [Software `superaske-augustine`](#software-superaske-augustine)
  - [Software `superaske-augustine_2`](#software-superaske-augustine_2)
- [Team `confucius`](#team-touche23-confucius)
  - [Software `chill-beagle`](#software-chill-beagle)
  - [Software `greedy-column`](#software-greedy-column)
  - [Software `swift-recipe`](#software-swift-recipe)
- [Team `johann-friedrich-herbart`](#team-touche23-johann-friedrich-herbart)
  - [Software `creative-suv`](#software-creative-suv)
  - [Software `wooden-taping`](#software-wooden-taping)
- [Team `mao-zedong`](#team-touche23-mao-zedong)
  - [Software `gold-developer`](#software-gold-developer)
  - [Software `hot-outpost`](#software-hot-outpost)
  - [Software `natural-frequency`](#software-natural-frequency)
- [Team `niccolo-machiavellie`](#team-touche23-niccolo-machiavellie)
  - [Software `adjacent-app`](#software-adjacent-app)
  - [Software `pointed-vertex`](#software-pointed-vertex)
- [Team `seyyed-hossein-nasr`](#team-touche23-seyyed-hossein-nasr)
  - [Software `genteel-hair`](#software-genteel-hair)
- [Team `t-m-scanlon`](#team-touche23-t-m-scanlon)
  - [Software `diachronic-suffix`](#software-diachronic-suffix)
  - [Software `matte-vehicle`](#software-matte-vehicle)

## Team `aristotle`
[See generic instructions above](#instructions)
### Software `1-baseline`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:aristotle-touche-human-value-detection-1-baseline-1-0-0-tira-docker-software-id-brilliant-ice -c 'python3 /1-baseline.py --inputDataset /tira-data/input --outputDataset /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/aristotle/1-baseline 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/aristotle/1-baseline", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `BERT cuda`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:aristotle-touche-human-value-detection-bert-1-0-1-cuda11-3-tira-docker-software-id-vicious-coverage -c 'python3 /app/predict.py --inputDataset /tira-data/input --outputDir /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/aristotle/BERT cuda 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/aristotle/BERT cuda", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `BERT nocuda`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:aristotle-touche-human-value-detection-bert-1-0-1-nocuda-tira-docker-software-id-savory-ton -c 'python3 /app/predict.py --inputDataset /tira-data/input --outputDir /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/aristotle/BERT nocuda 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/aristotle/BERT nocuda", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `Random baseline`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:aristotle-touche-human-value-detection-random-baseline-1-0-0-tira-docker-software-id-muted-banner -c 'python3 /random-baseline.py --inputDataset /tira-data/input --outputDataset /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/aristotle/Random baseline 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/aristotle/Random baseline", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `SVM`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:aristotle-touche-human-value-detection-svm-1-0-2-tira-docker-software-id-quick-magnitude -c 'python3 /app/predict.py --inputDataset /tira-data/input --outputDir /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/aristotle/SVM 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/aristotle/SVM", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `augustine-of-hippo`
[See generic instructions above](#instructions)
### Software `augustine`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:augustine-of-hippo-augustine-of-hippo-0-0-5-tira-docker-software-id-glad-directory -c 'python3 /augustine_of_hippo.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/augustine 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/augustine", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `mixture-augustine`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:augustine-of-hippo-mixture-augustine-of-hippo-0-0-13-tira-docker-software-id-exothermic-generator -c 'python3 /mixture_augustine_of_hippo.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/mixture-augustine 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/mixture-augustine", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `superaske-augustine`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:augustine-of-hippo-superaske-0-0-1-tira-docker-software-id-icy-berry -c 'python3 /augustine_of_hippo.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/superaske-augustine 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/superaske-augustine", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `superaske-augustine_2`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:augustine-of-hippo-superaske-0-0-22-tira-docker-software-id-buoyant-procedure -c 'python3 /augustine_of_hippo.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/superaske-augustine_2 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/augustine-of-hippo/superaske-augustine_2", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `confucius`
[See generic instructions above](#instructions)
### Software `chill-beagle`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-confucius-my-software-0-0-7-tira-docker-software-id-timid-list -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-confucius/chill-beagle 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-confucius/chill-beagle", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `greedy-column`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-confucius-my-software-0-0-3-tira-docker-software-id-sparse-tab -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-confucius/greedy-column 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-confucius/greedy-column", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `swift-recipe`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-confucius-my-software-0-0-4-tira-docker-software-id-worn-angel -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-confucius/swift-recipe 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-confucius/swift-recipe", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `johann-friedrich-herbart`
[See generic instructions above](#instructions)
### Software `creative-suv`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-johann-friedrich-herbart-johann-friedrich-herbart-0-0-1-tira-docker-software-id-free-edge -c 'python /jf_herbart/script.py --test /tira-data/input/arguments.tsv --checkpoint /jf_herbart/checkpoint.ckpt --out_predictions /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-johann-friedrich-herbart/creative-suv 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-johann-friedrich-herbart/creative-suv", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `wooden-taping`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-johann-friedrich-herbart-johann-friedrich-herbart-0-0-1-tira-docker-software-id-warm-tree -c 'python script.py --test /tira-data/input/arguments.tsv --checkpoint checkpoint.ckpt --out_predictions /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-johann-friedrich-herbart/wooden-taping 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-johann-friedrich-herbart/wooden-taping", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `mao-zedong`
[See generic instructions above](#instructions)
### Software `gold-developer`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-mao-zedong-my-software-0-0-5-tira-docker-software-id-concurrent-legend -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/gold-developer 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/gold-developer", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `hot-outpost`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-mao-zedong-my-software-0-0-6-tira-docker-software-id-tender-support -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/hot-outpost 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/hot-outpost", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `natural-frequency`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-mao-zedong-my-software-0-0-4-tira-docker-software-id-round-terry -c 'python /workspace/predict.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/natural-frequency 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-mao-zedong/natural-frequency", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `niccolo-machiavellie`
[See generic instructions above](#instructions)
### Software `adjacent-app`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-niccolo-machiavellie-submission-0-2-tira-docker-software-id-convex-sniffer -c '/T4_inference.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-niccolo-machiavellie/adjacent-app 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-niccolo-machiavellie/adjacent-app", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `pointed-vertex`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-niccolo-machiavellie-submission-0-1-tira-docker-software-id-coped-tub -c '/T4_inference.py --input /tira-data/input/arguments.tsv --output /tira-data/output/predictions.tsv'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-niccolo-machiavellie/pointed-vertex 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-niccolo-machiavellie/pointed-vertex", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `seyyed-hossein-nasr`
[See generic instructions above](#instructions)
### Software `genteel-hair`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-seyyed-hossein-nasr-bert-att-0-0-2-tira-docker-software-id-taxonomic-terrier -c 'python3 /code/app/main.py --inputDataset /tira-data/input --outputDataset /tira-data/output'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-seyyed-hossein-nasr/genteel-hair 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-seyyed-hossein-nasr/genteel-hair", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

---

## Team `t-m-scanlon`
[See generic instructions above](#instructions)
### Software `diachronic-suffix`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-t-m-scanlon-roberta-base-0-0-2-tira-docker-software-id-obsolete-score -c 'python plm/software.py --input /tira-data/input --output /tira-data/output --model_path /home/LanguageModels/roberta-base'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-t-m-scanlon/diachronic-suffix 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-t-m-scanlon/diachronic-suffix", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

### Software `matte-vehicle`
- [Docker](#description-docker):
  ```bash
  docker run --rm -ti -v $PWD/input:/tira-data/input:ro -v $PWD/output:/tira-data/output:rw --entrypoint sh docker.io/webis/valueeval-at-semeval-2023-human-value-detection-submissions:touche23-t-m-scanlon-roberta-base-0-0-2-tira-docker-software-id-mean-eel -c 'python plm/software.py --input /tira-data/input --output /tira-data/output --model_path /ckp/roberta-base-valid --device cpu'
  ```
- [TIRA (CLI)](#description-tira-cli):
  ```bash
  tira-run --input-directory $PWD/input --output-directory $PWD/output --approach valueeval-at-semeval-2023-human-value-detection/touche23-t-m-scanlon/matte-vehicle 
  ```
- [TIRA (Python)](#description-tira-python):
  ```python
  tira.run(identifier="valueeval-at-semeval-2023-human-value-detection/touche23-t-m-scanlon/matte-vehicle", input_dir=os.path.join(os.getcdw(), "input"), output_dir=os.path.join(os.getcdw(), output), dry_run=True)
  ```

