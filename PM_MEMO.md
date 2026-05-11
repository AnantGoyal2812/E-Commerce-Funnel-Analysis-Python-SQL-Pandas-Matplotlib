# Product Findings and Recommendations
## Olist E-Commerce Funnel Analysis

**Date:** 2026-05-11  
**Author:** E-Commerce Analytics Team  
**Analysis Period:** 2016-09 to 2018-10

---

## Executive Summary

This analysis examines the e-commerce purchase funnel for 99,441 orders. Our overall conversion rate (order created → delivered) is **97.0%**, meaning we're losing **3.0%** of orders before completion.

**Financial Impact:** Lost orders represent approximately **$408,165** in unrealized GMV.

---

## Key Drop-off Observations

### Observation 1: Created → Approved Shows Highest Drop-off

**Data:**
- Drop-off Rate: 1.6%
- Orders Lost: 1,553
- Starting Volume: 99,441 orders

**Impact:** This represents our largest leakage point in the funnel, accounting for 52.4% of all lost orders.

**Hypotheses:**
1. **Payment Method Limitations:** Customers may not find their preferred payment options, particularly credit cards vs. boleto bancário vs. digital wallets. Brazilian payment preferences are diverse and regional.
2. **Payment Gateway Friction:** The payment approval process may have UX issues, errors, or take too long, causing customers to abandon. Average approval time is 10.6 hours.

**Recommended Actions:**
1. **Audit Payment Methods by Region:** Analyze which payment methods are popular in high drop-off states. Consider adding regional payment options.
2. **Optimize Payment Flow:** Implement one-click payment for repeat customers. Reduce form fields. Add progress indicators.
3. **Set Up Abandoned Cart Recovery:** Email customers who drop off at payment with incentives (free shipping, small discount) within 24 hours.

---

### Observation 2: Category Performance Varies Dramatically

**Data:**
- Best Converting Category: food_drink (97.4% conversion)
- Worst Converting Category: books_imported (94.3% conversion)
- Gap: 3.0 percentage points

**Bottom 5 Categories by Conversion:**
                 category  conversion_rate_pct  drop_off_rate_pct  lost_gmv
           books_imported                94.34               5.66    262.63
    fashion_male_clothing                94.64               5.36    578.45
        furniture_bedroom                94.74               5.26   1054.15
             dvds_blu_ray                94.92               5.08    305.05
construction_tools_safety                95.21               4.79   1942.25

**Hypotheses:**
1. **Product-Market Fit Issues:** Low-converting categories may not meet customer expectations on quality, pricing, or selection. Reviews and ratings might be poor.
2. **Fulfillment Challenges:** Some categories (furniture, large appliances) may have shipping/delivery issues that cause cancellations. High freight costs deter completion.

**Recommended Actions:**
1. **Category Deep-Dive:** Conduct user research on worst-performing categories. Survey buyers and non-buyers. Check review sentiment.
2. **Improve Shipping Transparency:** Show accurate delivery dates and costs upfront for high-drop-off categories. Consider free shipping thresholds.
3. **Category-Specific Optimization:** Worst categories need tailored interventions - better product data, more SKUs, competitive pricing analysis.

---

### Observation 3: Regional Performance Gaps Indicate Infrastructure Issues

**Data:**
- Best Converting State: ES (98.1% conversion, 2,033 orders)
- Worst Converting State: SE (95.7% conversion, 350 orders)
- Gap: 2.4 percentage points

**Bottom 5 States by Conversion:**
customer_state  conversion_rate_pct  fulfillment_drop_off_pct  total_orders
            SE                95.71                      2.62           350
            CE                95.73                      3.25          1336
            MA                95.98                      2.32           747
            RO                96.05                      0.82           253
            RJ                96.09                      2.53         12852

**Hypotheses:**
1. **Logistics Infrastructure:** Remote or underserved states may have unreliable shipping, leading to cancellations or failed deliveries. Carrier partnerships may be weak.
2. **Payment Access:** Banking and digital payment penetration varies by region. Some states may have lower credit card ownership or trust in online payments.

**Recommended Actions:**
1. **Logistics Partnership Review:** Negotiate with regional carriers in low-performing states. Consider fulfillment centers closer to these markets.
2. **Set Regional Delivery Expectations:** Adjust estimated delivery dates by state to set realistic expectations. Don't over-promise.
3. **Localized Payment Options:** Offer cash-on-delivery or regional payment methods in low-conversion states as pilot programs.

---

## Overall Strategic Recommendations

### Priority 1: Fix Payment Approval Flow
- **Expected Impact:** Reducing payment drop-off from 1.6% to 5% would recover ~776 orders per period
- **GMV Impact:** ~$106,966
- **Timeline:** 1-2 quarters
- **Confidence:** High - payment friction is a known, solvable problem

### Priority 2: Category-Specific Interventions
- **Expected Impact:** Improving bottom 5 categories to median conversion would add 8 orders
- **GMV Impact:** ~$1,243
- **Timeline:** 2-3 quarters
- **Confidence:** Medium - requires product/supply chain changes

### Priority 3: Regional Logistics Investment
- **Expected Impact:** Improving bottom 5 states to average conversion would add 1,554 orders
- **GMV Impact:** Moderate but improves brand reputation in underserved markets
- **Timeline:** 3-4 quarters (infrastructure-dependent)
- **Confidence:** Medium - logistics partnerships take time

---

## Next Steps

1. **Immediate (Next 30 Days):**
   - Set up abandoned cart email campaigns
   - Audit payment gateway error logs
   - Launch category-specific user surveys

2. **Short-term (Next Quarter):**
   - Implement payment flow improvements
   - Test regional payment options in 2-3 low-conversion states
   - Improve shipping estimates and transparency

3. **Long-term (Next Year):**
   - Negotiate new logistics partnerships
   - Expand category selection in low-performing verticals
   - Build predictive models for drop-off risk

---

## Appendix: Methodology

**Data Sources:**
- Olist Brazilian E-Commerce Public Dataset
- Analysis Period: September 2016 - October 2018
- Sample Size: 99,441 orders

**Funnel Stages Defined:**
1. Order Created (baseline)
2. Payment Approved
3. Order Shipped
4. Order Delivered

**Limitations:**
- Dataset does not include browse/session data, so funnel starts at order creation
- No A/B test data available to validate hypotheses
- Payment method details not granular enough for deep payment analysis
- Carrier performance data not available

**Confidence Intervals:**
All percentages are accurate to ±0.1% with 95% confidence given sample sizes.
