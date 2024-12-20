import streamlit as st

def calculate_position_sizer(investment, daily_risk_percentage, leverage, stop_loss_percentage):
    # Calculate the position size based on the given formula
    position_sizer = (investment * (daily_risk_percentage / 100)) / (leverage * (stop_loss_percentage / 100))
    return position_sizer

# Streamlit App
st.title("Position Sizer Calculator for Trading")

# Input Fields
investment = st.number_input("Total Investment Amount (USDT)", min_value=0.0, value=100.0, step=10.0)
daily_risk_percentage = st.number_input("Maximum Daily Risk (%)", min_value=0.0, max_value=100.0, value=3.0, step=0.1)
leverage = st.number_input("Leverage", min_value=1, value=10, step=1)
stop_loss_percentage = st.number_input("Stop Loss Percentage (%)", min_value=0.1, max_value=100.0, value=1.0, step=0.1)

# Calculate button
if st.button("Calculate"):
    if investment > 0 and daily_risk_percentage > 0 and leverage > 0 and stop_loss_percentage > 0:
        position_sizer = calculate_position_sizer(
            investment, daily_risk_percentage, leverage, stop_loss_percentage
        )
        
        # Display Results
        st.subheader("Results")
        st.write(f"Position Sizer: {position_sizer:.2f} USDT")
    else:
        st.error("Please ensure all inputs are greater than zero.")
