OT-Guided Diffusion on MNIST

This repo contains a single end-to-end notebook that runs both phases:

Passive phase – train a small MNIST feature net, compute OT (Sinkhorn) and FID, and stress-test them (noise & missing classes).

Active phase – train a baseline DDPM and an OT-enhanced DDPM (loss = MSE + λ·OT in feature space), then evaluate and plot.

Files

CVLAB_25.ipynb – clean notebook (no outputs). Always renders on GitHub.

CVLAB_25_with_outputs.ipynb – same notebook with all results saved in-place (plots, printed metrics).

⚠️ GitHub cannot render this file because of a Jupyter widgets metadata issue.
Download it to view locally (or open in Colab).

How to view the results notebook (with outputs)

Option A — Local Jupyter

Download CVLAB_25_with_outputs.ipynb.

Open it in Jupyter Lab/Notebook: you’ll see all images and printed results.

Option B — Google Colab

Upload CVLAB_25_with_outputs.ipynb to Colab.

Open it; outputs will be visible without re-running.

Why GitHub shows “Invalid Notebook”: the file contains widget metadata (metadata.widgets/state) that GitHub’s renderer rejects. The notebook itself is valid—open it locally or in Colab to see everything.

Quick start (to re-run)

Colab (recommended)

Open CVLAB_25.ipynb in Colab.

(Optional) drive.mount('/content/drive') to save checkpoints/plots.

Run all cells.

Local

pip install torch torchvision
pip install git+https://github.com/lucidrains/denoising-diffusion-pytorch.git
pip install geomloss pot scipy scikit-learn wandb seaborn pandas tqdm


Then open CVLAB_25.ipynb and run cells top-to-bottom.

Outputs

Plots and tables are saved to _ddpm_plots/ (or your configured folder), including:

three_panel_comparison.png — Real | Before | After samples.

before_after_ot_fid.png — OT & FID bar charts (baseline vs OT-enhanced).

epoch_compare_* — OT/FID vs epoch (before/after).

combined_* — passive stress tests (noise ).

If you only want to inspect results, open CVLAB_25_with_outputs.ipynb locally/Colab.
If you want to reproduce everything, use CVLAB_25.ipynb.
