### 作业要求： 学习dureader 集成代码，补充 ensemble.py 219行开始的集成部分按照给定的weight：权重为 0.4, 0.2, 0.4 对三个模型的logit加权求完成ensemble 计算：start_logits， end_logits

- 1. weight 设定 (20)
- 2. start_logits 读取每个模型中的logit(20'),加和计算（20）
- 3. end_logits 读取每个模型中的logit(20),加和计算（20）

### 作业代码：
- 1. 在emsemble.py文的219～223行中加入了集成代码如下：
```python
        # TODO homework 补充模型集成代码 权重为 0.4, 0.2, 0.4 计算：start_logits， end_logits

        start_logits = 0.4 * start_logits1 + 0.2 * start_logits2 + 0.4 * start_logits3

        end_logits = 0.4 * end_logits1 + 0.2 * end_logits2 + 0.4 * end_logits3

```
- 2. 在run_dureader_albert.sh文件中设置数据路径DATA_DIR为本地的dev-v1.1.json等json文件的data路径为/Users/libo/Downloads/NLP05/Enterprise_Project/baidu_code/data，设置MODEL_NAME_OR_PATH路径为[hugging face website](https://huggingface.co/models)网站中已有的模型名称albert-xlarge-v2，代码如下：
```python
        export DATA_DIR=/Users/libo/Downloads/NLP05/Enterprise_Project/baidu_code/data
        export MODEL_NAME_OR_PATH=albert-xlarge-v2
```
其文件的路径如下：
[FILEPATH](file-path.png)

- MODEL_NAME_OR_PATH是通过该网站的搜索栏得到的，如下图所示
  [HUGGING FACE ALBERT XLARGE V2](hugging-face-albert-xlarge.png)

- 3. 通过以上1和2步的工作，在baidu_code文件根目录中运行```sh run_dureader_albert.sh``` ，mac电脑可以运行代码，但是由于mac不带GPU，运行过程非常缓慢，如下图所示：
[RUNNING RESULT](running_result.png)