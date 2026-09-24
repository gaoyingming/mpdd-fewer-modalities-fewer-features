# MPDD-AVG 2026 Young multimodal depression detection

this repository accompanies with the study on MPDD-AVG 2026 Young Track

## content

```text
code/
  repro_scripts/                         # clean and fast reproducibility scripts
  official_baseline/make_submission_forcodabench/
                                           # the format of official baseline and final submission
                                           
paper_reproducibility/ 				# all detailed reproducibility documents and files                                          
	experiments														# experiment
	final_pipeline												#	the final pipeline to run
	paper_snapshot												# paper documents
	stage_records													# intermediate records
	README.md															# the global readme file
	REPRODUCIBILITY_MATRIX.md							# the whole reproducibility matrix document
```

## reproducibility description

The main entry: `code/repro_scripts/run_pipeline.py`。
To prepare the data directory and dependency environment, please use：

```powershell
cd code
$env:BLEND_PHQ_THRESHOLD='4.25'
$env:TERNARY_T2='11.0'
$env:OUT_NAME='young_final_t4p25_t2p11'
python repro_scripts\run_pipeline.py
```

To run from scratch for retraining four facial ranker and ORIG backbones:

```powershell
cd code
$env:SKIP_CACHED='1'
python repro_scripts\run_pipeline.py
```

See installation requirements `code/repro_scripts/requirements.txt`。

## note

This repository does not contain the official dataset and model weights.
The complete training procedure requires the users to provides the data directories `Train-MPDD-Young/Young/` and `Test-MPDD-Young/Young/`.

