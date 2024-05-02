References

https://github.com/dreamgaussian/dreamgaussian/assets/25863658/db860801-7b9c-4b30-9eb9-87330175f5c8



## Install

```bash
pip install -r requirements.txt




## Usage

Image-to-3D:

```bash
### preprocess
# background removal and recentering, save rgba at 256x256
python process.py data/name.jpg




# train 500 iters (~1min) and export ckpt & coarse_mesh to logs
python main.py --config configs/image.yaml input=data/name_rgba.png save_path=name



### training mesh stage

python main2.py --config configs/image.yaml input=data/name_rgba.png save_path=name





