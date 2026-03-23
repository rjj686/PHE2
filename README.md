# 📊PHE<sup>2</sup> Dataset

 PHE<sup>2</sup>: A Chinese Document-level Dataset for Public Health Event Extraction

 PHE<sup>2</sup> can also be obtained from: 

## 📌 Overview

PHE<sup>2</sup> is a large-scale Chinese dataset for Document-level Event Extraction (DEE) in the public health domain. It is designed to support research on extracting structured event knowledge from long, complex public health news reports.

This dataset is constructed using a modular LLM-assisted annotation framework combined with human-in-the-loop quality control, ensuring both scalability and annotation quality.

- 📄 10,028 documents
- 📌 21,005 events
- 🧩 90,693 arguments
- 🏷️ 11 event types
- 🔑 57 argument roles

------

## 🏗️ Dataset Construction

PHE<sup>2</sup> is built using a four-module pipeline:

1. Event Schema Definition
2. Data Collection & Prompt Formulation
3. Multi-stage LLM Annotation
4. Human-in-the-loop Quality Control

### 🔹 Annotation Process

- **Stage 1**: Document-level Event Detection (ED)
- **Stage 2**: Schema-constrained Argument Extraction (EAE)

LLMs used:

- DeepSeek-R1 (event detection)
- DeepSeek-V3 (argument extraction)

------

## 🧾 Event Schema

### 📂 Event Types and Argument Roles

| 事件类型     | Event Type              |
| ------------ | ----------------------- |
| 水污染       | Water Pollution         |
| 疫情数据通报 | Epidemic Data Reporting |
| 确诊病例溯源 | Case Tracing            |
| 食物中毒     | Food Poisoning          |
| 食品筹建     | Food Sampling           |
| 药品上市     | Drug Launch             |
| 疫苗研发     | Vaccine Development     |
| 爱心捐赠     | Donation                |
| 纪念英雄     | Hero Commemoration      |
| 卫生宣传活动 | Health Campaign         |
| 环保项目中标 | Project Bid Winning     |

Detailed argument roles for each event type can be found in `schema.json`.

------

## 📊 Dataset Statistics

| Split     | Documents  | Events     | Arguments  |
| --------- | ---------- | ---------- | ---------- |
| Train     | 8,023      | 16,834     | 71,960     |
| Dev       | 1,002      | 2,221      | 10,008     |
| Test      | 1,003      | 1,950      | 8,725      |
| **Total** | **10,028** | **21,005** | **90,693** |

------

## 📁 Data Format

Each document is annotated as structured JSON:

```json
{
    "id": "7_262",
    "text": "天津1月26日电 (记者 张道正)记者26日上午从天津市疾控中心获悉，至1月26日6时，该市新增3例新型冠状病毒感染的肺炎确诊病例，确诊病例增至13例。第11例患者田某某，女，55岁，河北区人。1月23日出现发热、鼻塞等呼吸道症状到第四中心医院就诊。1月26日6时经市专家组确诊。目前已转至海河医院治疗。第12例患者韩某某，女，79岁，河北区人。于1月24日出现发热症状于第四中心医院就诊，1月26日6时经市专家组确诊。第13例患者陈某某，男，19岁，河北区人。1月20日出现发热、咽痛症状于天津市第四中心医院就诊，1月26日6时经市专家组确诊。目前，天津市新型冠状病毒感染的肺炎累计确诊13例，其中男性8例，女性5例；重症患者7例，轻症6例；无危重病例。追踪到密切接触者86例，其中已确诊3人，已解除医学观察2人，尚有81人正在接受医学观察。",
    "event_list": [
      {
        "trigger": "新增",
        "event_type": "疫情数据通报",
        "arguments": [
          {
            "role": "报道时间",
            "argument": "1月26日6时"
          },
          {
            "role": "疾病名称",
            "argument": "新型冠状病毒感染的肺炎"
          },
          {
            "role": "发布机构",
            "argument": "天津市疾控中心"
          },
          {
            "role": "通报区域",
            "argument": "天津市"
          },
          {
            "role": "新增确诊人数",
            "argument": "3例"
          },
          {
            "role": "累计确诊病例",
            "argument": "13例"
          }
        ]
      },
      {
        "trigger": "确诊",
        "event_type": "确诊病例溯源",
        "arguments": [
          {
            "role": "确诊主体",
            "argument": "田某某"
          },
          {
            "role": "确诊地点",
            "argument": "河北区"
          },
          {
            "role": "确诊时间",
            "argument": "1月26日6时"
          },
          {
            "role": "症状",
            "argument": "发热、鼻塞"
          }
        ]
      },
      {
        "trigger": "确诊",
        "event_type": "确诊病例溯源",
        "arguments": [
          {
            "role": "确诊主体",
            "argument": "韩某某"
          },
          {
            "role": "确诊地点",
            "argument": "河北区"
          },
          {
            "role": "确诊时间",
            "argument": "1月26日6时"
          },
          {
            "role": "症状",
            "argument": "发热"
          }
        ]
      },
      {
        "trigger": "确诊",
        "event_type": "确诊病例溯源",
        "arguments": [
          {
            "role": "确诊主体",
            "argument": "陈某某"
          },
          {
            "role": "确诊地点",
            "argument": "河北区"
          },
          {
            "role": "确诊时间",
            "argument": "1月26日6时"
          },
          {
            "role": "症状",
            "argument": "发热、咽痛"
          }
        ]
      }
    ]
  }
```

------

## 📖 Citation

If you find this dataset useful for your research, please consider citing our paper.

```bibtex

```
