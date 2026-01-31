
# RAG-Augmented LLMs for Stock Prediction 

This project explores how **Retrieval-Augmented Generation (RAG)** combined with **Large Language Models (LLMs)** can improve the accuracy of stock price predictions by leveraging historical data and news-based context.

## Objective

To enhance stock price prediction by combining:
- Statistical time series models (like RNNs, LSTMs, GRUs, Transformers)
- Company-specific financial/news insights using **RAG + FinBERT**
- A data-driven pipeline that integrates contextual and historical information for better multi-step forecasting

## Approach

- **Lookback window**: 30 days of historical data
- **Prediction target**: Next day (single-step) and next 7 days (multi-step)
- **Evaluation**: RMSE across 50 different stocks for model comparison
- **LLM module**: Outputs % change in price based on recent news context and past trends

## Models Explored

1. **RNN Architectures**: 
   - Vanilla RNN, GRU, LSTM
   - GRU offers a good balance of performance and computational cost

2. **Transformer-based Models**:
   - Single and Multi-head Attention
   - RMSE increases with poor attention head tuning

3. **FNet (Attention-free Transformer)**:
   - Used for multi-step forecasting with comparable performance

4. **RAG-Augmented FinBERT**:
   - Retrieves news headlines relevant to a company's performance
   - Embeddings generated via FinBERT’s [CLS] token
   - Output via regression predicts % increase or decrease in stock trend for the next month

## Sample RAG Query

```text
Filter and prioritize news headlines explicitly discussing factors influencing {company_name}'s stock price, including market trends, financial reports, corporate announcements, and industry-specific news impacting {company_name}'s performance.
```

## Output

- Forecasted **percentage change** in stock price trend (next month)
- RMSE used for quantitative comparison between models

## References

- [Soni et al., 2022 – Machine Learning for Stock Prediction](https://iopscience.iop.org/article/10.1088/1742-6596/2161/1/012065)
- [Su et al., 2024 – LLMs for Forecasting and Anomaly Detection](https://arxiv.org/abs/2402.10350)

## Author

**Harshit Tomar (2201AI15)**  
Under the guidance of **Dr. Jimson Mathew**  
IIT Patna, Innovation Lab Project
