# 股票行情获取Skill

## 描述
实时获取股票行情信息的skill，支持多种股票市场数据源。

## 功能
- ✅ 实时股票价格查询
- ✅ 历史行情数据获取
- ✅ 技术指标计算
- ✅ 多市场支持（A股、美股、港股等）
- ✅ 自定义时间范围查询

## 使用方法
```bash
# 获取实时行情
stock-quote get实时行情 股票代码

# 获取历史数据
stock-quote get历史数据 股票代码 开始日期 结束日期

# 获取技术指标
stock-quote 计算指标 股票代码 指标类型
```

## 支持的股票代码格式
- A股：600000（浦发银行）
- 美股：AAPL（苹果公司）
- 港股：00700（腾讯控股）

## 依赖
- Python 3.8+
- requests
- pandas
- numpy
- tushare（可选，用于A股数据）
- yfinance（可选，用于国际股票数据）

## 配置
在配置文件中设置数据源API密钥：
```yaml
data_sources:
  tushare: your_tushare_api_key
  yfinance: your_yfinance_api_key
```

## 安装
```bash
cd skills/stock-quote
./install.sh
```

## 示例
```python
from stock_quote import StockQuoteSkill

skill = StockQuoteSkill()

# 获取实时行情
quote = skill.get_real_time_quote("600000")  # 浦发银行

# 获取历史数据
historical = skill.get_historical_data("AAPL", "2023-01-01", "2023-12-31", "us")

# 计算技术指标
indicators = skill.calculate_technical_indicators("600000", ["MA", "MACD", "RSI"])
```