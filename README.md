# Nonlinear-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation
<h3> Introduction </h3>
<p> In this project, I use a set of data to estimate kinetic parameters of a fermentation model describing ethanol production in a batch bioreactor. The details of how these mathematical model can be described can be found from Fogler text book (i.e., Chemical Reaction Engineering, p. 365). These kinetic parameters are important to be estimated relibly because they are used in designing new reactors with larger sizes and different flow patterns (i.e., CSTR and Plug Flow). <br>
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
where subscripts c, s and p coressponds to microorganism, susbtrate (Glucose) and product (Ethanol). As shown, there are 9 parameters requiring estimation. Unfortunately, in the case study I used here there are only limited data for parameter estimation. The data set that are used for parmaeter estimation are shown in the following:
<img src='https://github.com/kaveh7293/Nonlinar-Regression-for-a-Model-Describing-Production-of-Ethanol-from-Glucose-Fermentatation/blob/main/Data.png'>
