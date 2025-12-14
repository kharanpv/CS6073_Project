[Original Repository](https://github.com/guilbera/colorizing.git)

# colorizing
![Alt text](B&W_color.png?raw=true)

This is a project that expands on the [medium's][1] article for colorizing black and white images using deep learning. The following improvements were made on the Pix2pix model
* **Pix2Pix** with self-attention model with spectral normalization

The dataset used for the training of the model can be downloaded [here][4] and originates from [here][5].

## Utilities
All the models use the pix utility (`/notebooks/utilities/pix.ipynb`) to copy the dataset from Google Drive to Google Colab and to convert RGB images to Lab images and vice versa. 

## Implemented Enhancements 

The current implementation incorporates several key improvements over baseline Pix2Pix: 

### Self-Attention Integration (SAGAN):

Adding self-attention mechanisms to both generator and discriminator transforms the architecture into a Self-Attention GAN (SAGAN). This enhancement enables long-range spatial dependency modeling, global color consistency across image regions, semantic understanding of object relationships, improved handling of large objects that span wide areas 

### Spectral Normalization:

Applied to every convolutional layer in both networks, spectral normalization provides improved training stability, balanced adversarial dynamics, reduced gradient explosion and vanishing, and faster convergence.

## Self Attention Implementation in Pytorch
The jupyter notebooks can be found in `/notebooks/pytorch_implementation/`.

`pix_pytorch.ipynb` contains the dataloader. 

`put_together_pytorch.ipynb` enables training the models in Google Colab.

## Pix2Pix Self Attention Model
The jupyter notebooks can be found in `/notebooks/pytorch_implementation/`. 

It uses the same dataloader as the beta and gamma model (`pix_pytorch.ipynb`). 

`pix2pix_model.ipynb` contains the Pix2Pix implementation, it can output either 2 channels (Lab implementation) or 3 channels (RGB implementation). 

`put_together_pix2pix.ipynb` enables training the models in Google Colab.

## Getting started

### Installing Model
1. got to `/models/model_download.md`
2. Got to the provided google drive link
3. Download the model locally and add it to the models folder
4. Imma send @Henock some files to finsh this H3

## Results

| Epoch | Image |
| ----- | ----- |
|   Black and White Baseline    |      ![image](/training/b&w.png) |
|   Epoch 60    |      ![image](/training/img-60.png) |
|   Epoch 80    |      ![image](/training/img-80.png) |
|   Epoch 95    |      ![image](/training/img-95.png) |
|   Actual    |      ![image](/training/train_color.png) |

| Discriminator Trainng Curve | Generator Training Curve |
| ----- | ----- |
| ![image](/training/discrim_loss.png)  | ![image](/training/gen_loss.png)  |

## Copyright
See [LICENSE](LICENSE) for details.  // Remove this on the low


[1]: https://anne-guilbert.medium.com/black-and-white-image-colorization-with-deep-learning-53855922cda6 "Black and White Image Colorization with Deep Learning"
[4]: https://drive.google.com/file/d/1hNXR_qPwNKS-z3xNQJ4fWlEWe-zES_nX/view?usp=sharing
[5]: https://www.floydhub.com/emilwallner/projects/color/43/data
