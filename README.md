# 家庭电器功耗数据分析（Python 数据分析汇报项目）

> Home Appliance Power Consumption Analysis  
> 课程：Python 数据分析
---

## 一、项目简介

本项目是 Python 数据分析课程大作业，基于多个家庭的小时级/分钟级用电数据，对家庭总功耗（Aggregate）、洗碗机（dishwasher）和洗衣机（washingmachine）进行数据清洗、探索性数据分析（EDA）和可视化分析。项目使用 Jupyter Notebook 完成，并最终形成英文项目报告。

主要任务包括：

1. 识别并处理错误数据记录：缺失值、重复值、负值、不规则时间间隔等。
2. 分析单个电器功耗与家庭总功耗之间的关系。
3. 从小时、工作日/周末、季度等维度进行可视化分析。
4. 总结家庭用电模式，并讨论可能的节能策略。

---

## 二、数据集说明

原始数据为多个 CSV 文件：

- `house1.csv`
- `house2.csv`
- `house3.csv`
- `house5.csv`
- `house6.csv`


每个 CSV 文件的主要字段如下：

| 字段 | 说明 | 单位 |
|---|---|---|
| `Time` | 时间戳，格式：`YYYY-MM-DD HH:MM:SS` | — |
| `Aggregate` | 家庭总功耗 | W |
| `dishwasher` | 洗碗机功耗 | W |
| `washingmachine` | 洗衣机功耗 | W |


---

## 三、项目结构

```text
home-appliance-power-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── README.md
│   └── house1.csv ... house6.csv
├── notebooks/
│   └── home_appliance_analysis.ipynb
├── report/
│   ├── final_report.pdf
│   └── final_report.docx
├── docs/
│   └── assignment_requirements.pdf
├── outputs/
│   └── figures/
└── src/
    └── analysis.py
```

---

## 四、主要分析内容

### 1. 数据清洗

- 统计缺失值数量与比例。
- 删除或填充缺失记录。
- 检测重复行与重复时间戳。
- 将负功耗值替换为 0。
- 按时间排序，处理不规则采样间隔。
- 根据功率与时间间隔计算能耗（kWh）。

### 2. 探索性数据分析（EDA）

- 每小时平均功率与总能耗。
- 洗碗机、洗衣机的活动时段。
- 工作日与周末用电模式对比。
- 季度能耗分布与家庭间对比。
- 单个电器对家庭总功耗的贡献。

### 3. 可视化图表

项目中使用了多种可视化方法，包括：

- 折线图：小时平均功率、工作日/周末对比。
- 柱状图与堆叠柱状图：家庭总能耗、季度能耗。
- 热力图：家庭 × 小时、家庭 × 季度。
- 环状图：季度能耗占比。
- 箱线图 / 小提琴图：周末与工作日能耗差异。

---

## 五、运行环境与使用方法

### 1. 安装依赖

```bash
pip install -r requirements.txt
```

`requirements.txt` 示例：

```txt
pandas
numpy
matplotlib
seaborn
jupyter
notebook
```

### 2. 准备数据

将 CSV 文件放入 `data/` 目录，例如：

```text
data/house1.csv
data/house2.csv
...
```

### 3. 运行 Notebook

```bash
jupyter notebook notebooks/home_appliance_analysis.ipynb
```

注意：Notebook 中读取 CSV 的路径写成自己的实际路径，例如：

```python
pd.read_csv("../data/house1.csv")
```

不要使用 `C:\Users\...` 这类本地绝对路径，否则下载后路径错误无法运行。

---

## 六、项目报告

最终报告位于：

```text
report/final_report.pdf
```

---

## 七、主要发现与结论

本项目通过数据清洗和可视化分析，得到以下主要发现：

1. 家庭总功耗在早晨和傍晚存在明显峰值。
2. 洗碗机和洗衣机的使用时段相对集中，对总功耗峰值有一定贡献。
3. 工作日与周末的用电模式存在差异，周末白天用电量通常更高。
4. 不同家庭之间的季度能耗分布差异明显，说明生活习惯对用电影响较大。
5. 通过错峰使用大功率电器，可以在一定程度上降低峰值负荷。

---

## 八、学术诚信声明

本项目代码与报告为个人课程作业，仅用于学习与交流。  
禁止直接复制、抄袭本项目内容用于提交作业。  
报告中引用的代码、资料和技术来源已在 References 中说明。

---

## 九、作者

- 姓名：He Yangyang
- GitHub：[Bravo_18]

---

## 十、License

本项目仅用于课程学习，未添加正式开源许可证。如需引用，请联系作者。