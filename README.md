# Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation
<h3> Introduction </h3>
<p> In this project, I use a set of data to estimate kinetic parameters of a fermentation model describing ethanol production in a batch bioreactor. The details of how these mathematical model equations were obtained can be found from Fogler text book (i.e., Chemical Reaction Engineering, p. 395). These kinetic parameters are important to be estimated relibly because they are used in designing new reactors with larger sizes and different flow patterns (i.e., CSTR and Plug Flow). <br>
The only data that are available for parameter estimation is concentration of Glucose in different reaction times. The data values for some of the reactions times are shown below:<br>
<table>
  <tr>
    <th>Time (hr)</th>
    <th>Concentration (g/lit)</th>
  </tr>
  <tr>
    <td>1</td>
    <td>1.7607283</td>

 </tr>
  <tr>
    <td>1.5</td>
    <td>6.89</td>
 </tr>
 <tr>
    <td>2</td>
    <td>11.62</td>

 </tr>
<tr>
    <td>2.5</td>
    <td>12.69</td>

 </tr>
 <tr>
    <td>11</td>
    <td>93.59</td>

 </tr>

<tr>
    <td>11.5</td>
    <td>91.44</td>

 </tr>

<tr>
    <td>12</td>
    <td>94.39</td>

 </tr>

</table><br>
The model equations describing ethanol productions are shown as follows:
<img src='https://github.com/kaveh7293/Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/Bioreactor_equations.png'>
where subscripts c, s and p coressponds to microorganism, susbtrate (Glucose) and product (Ethanol). As shown, there are 9 parameters requiring estimation. Unfortunately, in the case study I used here there are only limited data for parameter estimation. The data set that are used for parmaeter estimation are shown in the following:<br>
<img src='https://github.com/kaveh7293/Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/Data_2.png'><br>
To estimate the parameters, I used solve_ivp from scipy.integrate in python to solve the three ODE equations (1) to (3). I then used minimize from scipy.optimize to minimize the corresponding objective function. The values of final estimated parameters are:
<img src='https://github.com/kaveh7293/Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/Parameter_estimates.png'>
The corresponding model fit to the data can be seen in the following figure:
<img src='https://github.com/kaveh7293/Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/Model_predictions.png'>
as shown, the model fit to the data is very good.
<h4>Parameter Uncertainty Quantification </h4>
<p>Unfortunately, it is not possible to obtain confidence intervals for the parameter estimates using linearization based approach, because the Fisher Information Matrix for the parameters is not invertible. I believed that this is becuase of the correlative effects between the parameter estimates. To obtain information about parameter uncertainties, I used a Monte Carlo simulation by randomly generating 50 new data set and obtaining parameter estimates. I then used these MC-based parameter estimates to find out which parameters are correlated and to find out the extent of uncertainties in parameters. In the following you can see the heatmap for the parameter estimates based on 50 MC simulations:<br>
<img src='https://github.com/kaveh7293/Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/MC_parameters_.png'>

</p>
