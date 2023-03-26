# PM2.5 Level Prediction

The purpose of this project was to predict PM2.5 particulate levels for cities in mainland China. This was done using two different time series models; a SARIMA model and an ARMA-GARCH model. Prediction for this project was done only for Beijing (due to time constraints), but the process could be extended to any other location. Each city in China has multiple recording sites for each city. In Beijing, there were four different recording sites.

1. `Dongsi`
2. `Dongsihuan`
3. `Nongzhanguan`
4. `US Post` (US Weather Post)

Dongsi was chosen as the recording station to use as there was only enough time to do the process for one station. The [original data](https://github.com/pholaway72/PM2.5_Level_Prediction/blob/main/Data%20Sets/BeijingPM20100101_20151231.csv) contained hourly readings of PM2.5 particulate levels, however, the model was trained on the daily average. When using the hourly readings, there was too much noise from the data which led to highly innacurate models.

The final models considered were...

| Model | 5-Day RMSE | 1-Month RMSE |
| :---: | :---: | :---: |
| SARIMA(0,0,2)x(0,1,1)_14 | 1.7617 | 2.7543 |
| ARMA(1,1)-GARCH(1,2) | 1.7521 | 4.8082 |

The ARMA-GARCH model however we found to be more realistic as its predictions had a gradual decline from the high in January. The SARIMA model's predictions immediately dropped to PM2.5 levels of below 100. A description of the data set, methodologies used, and results can be found in the [Project Report](https://github.com/pholaway72/PM2.5_Level_Prediction/blob/main/429FinalProject_Holaway_Li_Nagel.pdf) and or the [Project Presentation Video](https://github.com/pholaway72/PM2.5_Level_Prediction/blob/main/Presentation%20Video/video2809821395.mp4). All code is located in the [Project Sandbox](https://github.com/pholaway72/PM2.5_Level_Prediction/blob/main/Project-Sandbox.Rmd).
