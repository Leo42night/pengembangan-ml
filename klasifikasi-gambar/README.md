# Klasifikasi Gambar
- Dataset Kaagle [**puneet6060/intel-image-classification**](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)
  - Total: **24335 Files**
    - Train: 14034 files 
    - Test: 3000 files 
    - Prediction: 7301 files

## Split File
- Train dibagi 80/20:
  - 11224 data_train/train
  - 2810 data_train/val

## Model

### Compile
| Layer (type)             | Output Shape         | Param #       |
|--------------------------|----------------------|---------------|
| conv2d (Conv2D)          | (None, 126, 126, 32)| 896           |
| max_pooling2d (MaxPooling2D) | (None, 63, 63, 32) | 0             |
| conv2d_1 (Conv2D)        | (None, 61, 61, 64)  | 18,496        |
| max_pooling2d_1 (MaxPooling2D) | (None, 30, 30, 64) | 0          |
| conv2d_2 (Conv2D)        | (None, 28, 28, 128) | 73,856        |
| max_pooling2d_2 (MaxPooling2D) | (None, 14, 14, 128) | 0          |
| conv2d_3 (Conv2D)        | (None, 12, 12, 256) | 295,168       |
| max_pooling2d_3 (MaxPooling2D) | (None, 6, 6, 256)  | 0           |
| flatten (Flatten)        | (None, 9216)        | 0             |
| dense (Dense)            | (None, 256)        | 2,359,552     |
| dropout (Dropout)        | (None, 256)        | 0             |
| dense_1 (Dense)          | (None, 4)          | 1,028         |

**Total params:** 2,748,996 (10.49 MB)  
**Trainable params:** 2,748,996 (10.49 MB)  
**Non-trainable params:** 0 (0.00 B)

### Fit
- epoch 100
- callback
  - checkpoint
  - early stopping: val_loss dengan patience 10

## Akurasi
### - Training Set: 0.9250
### - Validation/Test Set: 0.8779
### - Testing Set: 0.8841