## 训练模型

### 数据集

使用DIV2K数据集的800张图片作为训练数据，此外将所有图片下采样到一半加入训练数据中。

将1600张图片放到```IMAGE_PATH```.

### 命令

命令示例如下,

```CUDA_VISIBLE_DEVICES=0,1 python train.py train --batchsize 16 --train_glob "IMAGE_PATH/*.png" --checkpoint_dir checkpoint --lambda 0.004```



## 运行

在运行前先编译算术编码器：

```g++ module_arithmeticcoding.cpp -o module_arithmeticcoding```


### 编码(使用GPU)
```python AppEncDec.py compress example.png example.bin --qp 1 --model_type 0 --device cuda```

### 解码(使用GPU)
```python AppEncDec.py decompress example.bin example_dec.png --device cuda```
