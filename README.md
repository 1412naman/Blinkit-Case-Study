# Blinkit Case Study

## Data Analysis: Upfront Pricing Precision for Ride-Hailing Services

### Project Overview
This project focuses on analyzing the precision of upfront pricing in ride-hailing services (e.g., Uber, Ola). The goal is to identify key opportunities to improve the accuracy of upfront pricing to ensure a smoother customer experience and reduce instances of pricing surprises.

### Data Description
The data used in this analysis contains the following key variables:

- **order_id_new**: ID of an order.
- **order_try_id_new**: ID of an attempt to complete an order.
- **calc_created**: Timestamp when the order was created.
- **metered_price**: The actual price based on distance and time.
- **upfront_price**: The price predicted and shown to the rider before the ride.
- **distance**: Actual distance of the ride.
- **duration**: Actual duration of the ride.
- **gps_confidence**: Indicator for GPS connection quality (1 - good, 0 - bad).
- **entered_by**: Indicates who entered the address.
- **b_state**: State of the ride (e.g., finished).
- **dest_change_number**: Number of destination changes made by the rider or driver.
- **predicted_distance**: Predicted distance based on pickup and dropoff points.
- **predicted_duration**: Predicted duration based on pickup and dropoff points.
- **prediction_price_type**: Type of price prediction:
  - `upfront, prediction`: Prediction before the ride.
  - `upfront_destination_changed`: Prediction after a destination change.
- **change_reason_pricing**: Reason for a change in the price prediction.
- **ticket_id_new**: Customer support ticket ID.
- **device_token, device_token_new**: Device token ID (empty for all fields).
- **rider_app_version**: App version on the rider’s phone.
- **driver_app_version**: App version on the driver’s phone.
- **driver_device_uid_new**: Device UID of the driver’s phone.
- **device_name**: Name of the device.
- **us_indicator**: Indicates whether the ride took place in the US.
- **overpaid_ride_ticket**: Indicator if the rider complained about overpaying.
- **fraud_score**: Rider's fraud score (the higher, the more likely to cheat).

### Objective
To analyze the data and identify the top 1-2 opportunities for improving upfront pricing precision. The findings will be compiled into a business report that caters to both technical and business stakeholders.

### Result
There is a negative correlation between price difference and both distance (-0.17) and duration (-0.16). This means that longer rides (in terms of distance and time) tend to have smaller discrepancies between upfront and metered prices.
GPS confidence has a very weak correlation with price difference, implying it might not be a significant factor in pricing accuracy.
Destination changes also show a weak negative correlation (-0.025) with price difference, indicating that it may have a minor impact on discrepancies.

## Opportunities for Improvement:
**Improve pricing models for short-distance rides:** The negative correlation with distance suggests that shorter rides tend to have greater price discrepancies. Focusing on improving the precision of pricing for these rides could help reduce surprises for customers.

**Handle outliers more effectively:** There are a few extreme cases where the price discrepancy is exceptionally large. These could be investigated further to understand whether they stem from unusual circumstances (e.g., significant destination changes, technical errors) and addressed specifically in the pricing algorithm.


**GPS Confidence = 1 (Good GPS):** The majority of rides with good GPS have a tighter distribution of price differences. This suggests more accurate upfront pricing.

**GPS Confidence = 0 (Poor GPS):** Rides with poor GPS confidence tend to show more variability in price discrepancies, indicating that unreliable GPS signals can contribute to larger pricing errors.
