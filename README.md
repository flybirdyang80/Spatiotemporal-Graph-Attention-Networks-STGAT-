# Satellite-Based Reconstruction of High-Resolution Ocean Subsurface Temperature Using Spatiotemporal Graph Attention Networks-

This study proposes a Spatiotemporal Graph Attention Network (STGAT) that integrates a Temporal Convolutional Network (TCN), a Graph Attention Network (GAT), and two channel attention mechanisms.. Using only satellite-derived sea surface observations, the proposed model achieves high-accuracy reconstruction of ocean subsurface temperature fields at 21 depth levels ranging from 20 to 1941 m in the Kuroshio Extension region. The model training code has been open-sourced to facilitate reuse and further development. The study area covers the Kuroshio Extension (138°–158°E, 30°–40°N).。

data:


Data	Source	Resolution

SLA	CMEMS	0.125°

SST	UKMO	0.05°

SSS	CNR	0.125°

SSW	CCMP	0.25°

Reanalysis	GLORYS12V1	0.083°

EN4	UKMO Hadley Centre	\

   

Data preprocessing includes cropping the study domain to the Kuroshio Extension region, bilinear resampling to a spatial resolution of 0.25°, and unifying all datasets to a daily temporal resolution. Standardization is applied to all input variables. A derived variable, termed Depth-Specific Temperature Anomaly Gradient (DSTAG), is constructed by subtracting the six-year mean temperature at each depth from the sea surface temperature (SST) and then normalizing by depth. In total, 21 depth levels are selected (20 m, 30 m, 40 m, 55 m, 77 m, 110 m, 155 m, 186 m, 266 m, 318 m, 380 m, 453 m, 541 m, 643 m, 763 m, 902 m, 1062 m, 1245 m, 1452 m, 1684 m, and 1941 m). Data from 2017–2021 are used for model training, while data from 2022 are reserved for testing.

<img width="865" height="268" alt="image" src="https://github.com/user-attachments/assets/fd6e2bd0-9a42-4556-b7fc-938335e6e4a0" />



Innovations: This study is the first to apply a spatiotemporal graph attention network to ocean subsurface temperature reconstruction. A derived variable, termed DSTAG, is introduced to enhance vertical constraints, while both EN4 in situ observations and the GLORYS12V1 reanalysis data are jointly incorporated in the loss function.
Results: The reconstructed temperature fields achieve an average RMSE of 0.916°C and an R² of 0.866 when evaluated against the GLORYS12V1 reanalysis data. The proposed method outperforms baseline models, including CNN and Attention U-Net, and demonstrates stable errors across spatial, temporal, and vertical dimensions.

