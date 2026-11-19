# Predictive Analytics for Inventory & Resource Planning

**Planned build · Python, scikit-learn, SQL, Streamlit and Power BI**

**Decision.** At a weekly planning review, purchasing needs to know which yarns or coatings require an order and which apparent shortages can wait. Quantify the forecast error separately from the inventory consequences of acting on it.

| Milestone | Work | Acceptance check |
|---|---|---|
| 1. Define demand | Build weekly finished-goods order demand by SKU. Specify a four-week horizon, bill of materials, yields, supplier lead times, stock on hand and scheduled receipts. | Trace one finished-product order into yarn kilograms and coating litres with explicit unit conversions. |
| 2. Build the benchmark | Compare a last-observed-demand forecast with a Random Forest using lagged demand, shifted rolling statistics and calendar features known at the forecast date. | Evaluate both on identical rolling forecast origins. Reserve a final chronological holdout and exclude future orders or realised production from features. |
| 3. Evaluate decisions | Report mean absolute error (MAE) per SKU and weighted absolute percentage error (WAPE) for groups with compatible units. Compare against the baseline on the holdout. Translate finished-goods forecasts into gross material needs and net against stock and receipts. | Test a 15% relative WAPE reduction. Under the same reorder policy, compare stockout weeks and average inventory value. Report trade-offs and flag any zero-demand denominator. |
| 4. Deliver the planner view | Add filters for SKU, forecast origin and horizon in Streamlit. Display actuals, both forecasts, projected stock and suggested order dates. Export a dated forecast table for Power BI. | Publish a reproducible backtest, planner walkthrough, limitations and a Power BI import guide. Explain how synthetic demand, uncertain yields and supplier delays affect interpretation. |

**Metric example.** A baseline WAPE of 40% and model WAPE of 34% would give a 15% relative error reduction. These values illustrate the calculation. Inventory impact requires a separate replenishment test.

**First session.** Specify the weekly demand table and work through a single SKU, two raw materials and one outstanding purchase order. Check the hand-calculated net requirement before fitting a model.
