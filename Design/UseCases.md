# Actors
- **Investor**: This user will be interacting with our frontend to generate an Investment Policy statement.
---
# Use Cases
- **UC1**: **Risk Tolerance Survey** Investor will complete a risk tolerance survey to estimate risk tolerance in the portfolio.
  - Why?: this is a use case because an IPS needs an estimate of risk to determine which securities to invest in
  - Actors: **Investor**
  - flow: login -> risk tolerance survey
  - business req's: B1
- **UC2**: **Obtain a pdf of the portfolio plan** Investor will obtain a complete pdf of the finished investment policy statement.
  - Why?: The Investor needs to sign the document in order for the investment policy statement to be valid. Therefore the Investor must be able to obtain a pdf copy of the ips
  - Actors: **Investor**
  - flow: login -> risk tolerance survey -> objectives -> strategy -> obtain pdf
  - business req's: B1
- **UC3**: **Investment Objectives** Investor will be prompted to enter an objective for the portfolio
  - Why?: The main function of an ips is to ensure that the portfolio is meeting the Investment objectives, so they must be specified.
  - Actors: **Investor**
  - flow: login -> risk tolerance survey -> objectives
  - business req's: B1
