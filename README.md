# crf_torch_onnx
可以转成onnx的torch版本的CRF
从如下代码改造得来：
https://github.com/taishan1994/pytorch_bert_bilstm_crf_ner/blob/16ee44df462dfa9fde13597d724ea9f6477ef935/layers/CRF.py

## torch CRF 转onnx
torch的CRF在转ONNX的时候，因为里面有一些for循环，trace会导致seq_length固定，无法支持变长，准确率有问题，所以一般是trace和script混合着用。

## 版本说明：
onnx==1.15.0
onnxruntime-gpu==1.17.1
torch==2.0.1+cu117
