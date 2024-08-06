## GENERALIZED GROUND MOTION PREDICTION MODEL (GGMPM) 

This tool, named as Generalized Ground Motion Prediction Model (GGMPM), uses a hybrid Recurrent Neural Network (RNN) framework to estimate a 29x1 correlated vector (denoted as IM) of RotD50 Spectral Acceleration (Sa) at 26 periods and geometric means of Arias Intensity (Ia), Significant Duration (D5-95) and Cumulative Absolute Velocity (CAV) using a set of seismic source and site parameters as inputs. The source and site inputs to the RNN framework include a vector of 12 values including F, M, Rrup, Rx, RJB, DHyp, ZTOR, Vs30,. The discrepancy between the IM vector predicted using the RNN framework and the computed from recorded ground motions is further minimized by using the Covariance Matrix Adaptation Evolution Strategy (CMA-ES). The residuals of the RNN framework are used to construct the inter-event and the intra-event covariance matrices to account for the inter-event and intra-event variabilities of the ground motions. Hence, given the source and site parameters, this tool returns a median prediction of the IM and estimated inter-event and intra-event covariance matrices. The executable is developed by Jawad Fayaz (https://jfayaz.github.io/layouts/codeandsoft.html/) and research team at University of California- Irvine (UCI). The program is named as "Generalized Ground Motion Prediction Model (GGMPM)". For further details please read the article mentioned in the "Reference".

Download the application from the following Dropbox link

    https://www.dropbox.com/scl/fo/sr9ev6y2ggeg69fctxiiv/AIuJIWrRGeJX7HT1Bns9uS4?rlkey=xzxxziqvd52q4ozvhlkcahnfc&dl=0


1. 	GGMPM Inputs (in order)

          Fault Mechanism (F)
                                Mechanism (F)
                                Strike Slip -	1
                                Normal -	2
                                Reverse -	3
                                Reverse Oblique - 4
                                Normal Oblique -  5

          Magnitude (Mw)
          Closest Rupture Distance (Rrup) in kilometers (km)
          Depth to Top of Rupture (ZTOR) in kilometers (km)
          Distance Measure (Rx) in kilometers (km)
          Joyne-Boore Distance (RJB) in kilometers (km)
          Hypocentral Distance (DHyp) in kilometers (km)
          Shear-Wave Velocity (Vs30) in meters per second (m/s)
          Conditional Period (T*) in seconds (s)
  
  
2.	Calling GGMPM  

The tool package consists of the executable application "GGMPM_Predictions.exe" which can be easily called from any command line or programming language/software. The generalized syntax to run the executable is as follows:

          GGMPM_Predictions.exe   F   Mw   Rrup   ZTOR   Rx   RJB   DHyp   Vs30   T*
 
 
3. 	GGMPM Outputs

The tool provides outputs in "RESULTS" folder (name of the "RESULTS" folder is preceded by a serial number) within the framework folder. The outputs consist of two files: 1)"GGMPM_Outputs.xlsx" excel file containing the estimated predictions and 2)"GGMPM_Sa_Spectra.jpg" picture file showing the median and sigma bands of the estimated RotD50 spectral acceleration. The excel file "GGMPM_Outputs.xlsx" includes three sheets 1)"Conditional_Predictions_log" provides the median and correlated sigma predictions of the 29 IMs in log-scale (note: the estimated median vector is correlated without any conditional period; estimated sigma vector is correlated with conditional period T* inputted by the user), 2)"IntraEvent_SigmaCov_log" provides Within-Event covariance matrix of the predictions in log-scale, and 3)"InterEvent_TauCov_log" provides Between-Event covariance matrix of the predictions in log-scale. The Intra-Event and Inter-Event variabilities are combined to provide the overall sigma vector in sheet "Conditional_Predictions_log".
 


Reference
    
    Jawad Fayaz, Yijun Xiang, and Farzin Zareian (2020). "Generalized Ground Motion Prediction Model (GGMPM) using Hybrid Neural Networks". Structural Dynamics and Earthquake Engineering. https://onlinelibrary.wiley.com/doi/epdf/10.1002/eqe.3410

