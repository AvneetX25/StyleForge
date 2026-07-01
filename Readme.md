# StyleForge 🎨

A Flask web application for **Neural Style Transfer** using **AdaIN (Adaptive Instance Normalization)**. Upload a content image and a style image, and StyleForge generates a stylized output blending the two in real time.

## Demo

<!-- PASTE THE GITHUB-GENERATED VIDEO LINK HERE AFTER DRAG-AND-DROP UPLOAD -->
<!-- Example format: https://github.com/user-attachments/assets/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -->


## Features

- Upload custom **content** and **style** images through a simple web UI
- Real-time style transfer using a pretrained **AdaIN** decoder
- Example content/style images included for quick testing
- Built with **Flask** + **PyTorch**

## Tech Stack

- **Backend:** Flask, Flask-WTF
- **Deep Learning:** PyTorch, Torchvision
- **Model:** Pretrained VGG (`vgg_normalised.pth`) + custom-trained AdaIN decoder (`decoder_final.pth`)
- **Frontend:** HTML/CSS/JS (Jinja templates)

## Project Structure

```
StyleForge/
├── content_dataset/       # Training content images
├── style_dataset/         # Training style images
├── examples/               # Sample content/style images for the demo UI
├── experiment/
│   └── decoder_final.pth  # Trained AdaIN decoder weights
├── sample_content/
├── sample_style/
├── static/                 # CSS/JS assets
├── templates/
│   └── index.html          # Main web UI
├── utils/                   # Helper functions/modules
├── app.py                   # Flask application entry point
├── train.py                  # Script to train the AdaIN decoder
├── vgg_normalised.pth        # Pretrained VGG weights
└── requirements.txt
```

## Model Weights

The pretrained model weights are **not included in this repository** (too large for git). Download them separately and place them in the correct folders:

- `vgg_normalised.pth` → place in the project root


https://github.com/user-attachments/assets/9920fcbd-92bf-4975-a0d1-8f33fc178cb8



<!-- ADD YOUR DOWNLOAD LINK(S) HERE, e.g. Google Drive / Hugging Face -->

## Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/AvneetX25/StyleForge.git
   cd StyleForge
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   ```
   Activate it:
   - Windows: `venv\Scripts\activate`
   - Mac/Linux: `source venv/bin/activate`

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the app**
   ```bash
   python app.py
   ```

5. **Open in browser**
   ```
   http://127.0.0.1:5000
   ```

## Known Issues / Notes

- On Windows with Anaconda, you may hit an OpenMP conflict (`OMP: Error #15`). If so, set:
  ```bash
  set KMP_DUPLICATE_LIB_OK=TRUE      # Windows CMD
  $env:KMP_DUPLICATE_LIB_OK="TRUE"   # PowerShell
  ```

## Training

To train your own decoder on custom content/style datasets:
```bash
python train.py
```
Adjust dataset paths and hyperparameters inside `train.py` as needed.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## Author

**Avneet** ([@AvneetX25](https://github.com/AvneetX25))
