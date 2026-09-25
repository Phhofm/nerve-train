# NERVE — training

**NERVE links:** [models & configs](https://huggingface.co/Phips/NERVE) · [try it online (ZeroGPU)](https://huggingface.co/spaces/Phips/nerve) · [local app](https://github.com/Phhofm/nerve-app) · [train your own (Colab)](https://github.com/Phhofm/nerve-train)

Train your own [NERVE](https://huggingface.co/Phips/NERVE) model.

## Google Colab (easiest, free GPU)

Open **[`nerve_train_colab.ipynb`](nerve_train_colab.ipynb)** in Colab
(*File → Open notebook → GitHub*, or upload it), then run the cells in order.
The last cell gives you a small form:

- **Scale**: 4x / 2x / 1x
- **Data**: OTF degradation (HR folder only) or paired HR/LR folders
- optional **validation** HR/LR folders
- **Iterations** and a run **name**
- press **Start training**

It clones traiNNer-redux, drops in the NERVE architecture, and trains. Put your
images in Google Drive (the notebook mounts it for you).

## Locally

NERVE is a normal traiNNer-redux architecture:

```bash
cp nerve_arch.py <traiNNer-redux>/traiNNer/archs/
cp icnr.py       <traiNNer-redux>/traiNNer/utils/
cp configs/4x_NERVE_release.yml <traiNNer-redux>/options/
cd <traiNNer-redux>
python train.py -opt options/4x_NERVE_release.yml --auto_resume
```

Sample configs and released pretrains (great warm-starts) live at
[huggingface.co/Phips/NERVE](https://huggingface.co/Phips/NERVE).

Apache-2.0.
