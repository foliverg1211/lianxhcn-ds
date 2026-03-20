# 中国主要城市公共预算支出和收入数据分析

## 项目说明

本项目分析中国主要城市的财政收支状况，计算各城市的预算缺口（财政赤字），并从多个维度进行可视化分析。

## 数据来源

- **国家统计局**：[https://data.stats.gov.cn/easyquery.htm?cn=E0105](https://data.stats.gov.cn/easyquery.htm?cn=E0105)
  - 首页 >> 地区数据 >> 主要城市年度数据
  - 财政和金融：
    - 地方一般公共预算收入 → `city_income.xlsx`
    - 地方一般公共预算支出 → `city_expenditure.xlsx`
    - 住户存款余额 → `individual_deposit.xlsx`
  - 国民经济核算：
    - 地区生产总值（当年价格）(亿元) → `gdp.xlsx`

## 数据字典

| 变量名 | 说明 | 单位 |
|--------|------|------|
| city | 城市名称 | - |
| year | 年度 | - |
| income | 地方一般公共预算收入 | 亿元 |
| expend | 地方一般公共预算支出 | 亿元 |
| deposit | 住户存款余额 | 亿元 |
| gdp | 地区生产总值 | 亿元 |
| gap | 预算缺口（expend - income）| 亿元 |
| gap_to_gdp | 预算缺口占GDP比例 | - |

## 项目结构

```
T2_城市财政赤字分析/
├── README.md                    # 项目说明
├── 01_data_crawl.ipynb          # 数据爬取
├── 02_data_analysis.ipynb       # 数据分析与可视化
├── data_raw/                    # 原始数据
│   ├── city_income.xlsx
│   ├── city_expenditure.xlsx
│   ├── individual_deposit.xlsx
│   └── gdp.xlsx
├── data_clean/                  # 清洗后数据
│   └── merged_data.xlsx
└── output/                      # 输出图形和表格
    ├── gap_to_gdp_top_bottom.xlsx
    ├── growth_rate.xlsx
    └── *.png (可视化图形)
```

## 分析内容

1. 计算每个城市每年的预算缺口 (gap) 和 gap_to_gdp
2. 计算 income 和 expend 的年度增长率
3. 特定年份（2006, 2010, 2014, 2018, 2022）gap_to_gdp 最大/最小城市
4. 北上广深 gap_to_gdp 对比分析
5. 珠三角 vs 长三角城市对比分析
6. 房地产角度分析 gap_to_gdp 地区差异和时序特征
