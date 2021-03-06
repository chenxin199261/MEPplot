

# MEPplot
 [中文](README_CN.md)  [日本語](README_JP.md)

<a href="https://explosion.ai"><img src=".\ui\Logo.png"  width="225" height="185" align="right" /></a>

A GUI program for plotting minimal energy path on potential energy (or free energy) surface. This program is based on string method. Please refer to this paper (Phys. Rev. B **66**, 052301 – Published 12 August 2002) for details.




## Download and  Installation

Find the latest `.rar` file here:

https://github.com/chenxin199261/MEPplot/releases

or

https://mega.nz/folder/hsVzVSKT#3IEzoJZzkmEQZJACTAEcMQ

For users in mainland China (GitHub is slow), please use the following address:

https://n459.com/file/30374101-473325811  （passwd: 111111）

Download rar file and unzip the file. You will see 3 files.

* MEPplot.bat : Entry of MEPplot, executable file.
* example: Template PES.
* main: Program files.



## Usage

Double click the file `MEPplot.bat`. The following interface will be showed. Please follow the instructions step by step.

<img src=".\Readme-figures\R2.png" alt="R2"  />

#### 1. Prepare potential energy surface (PES) data file

Your 2D PES file should be prepared in specific format strictly. The file contains 3 columns (X, Y and Energy) as following examples,

```
  -0.88235    1.99224   30.64485
   1.23646   -0.78346  420.58113
   1.03326    0.21343   18.23895
  -1.28864    1.87634   23.34170
   0.22373    0.08548  -79.56263
   0.97433    0.60216  119.97031
   0.03879   -0.50717   55.13104
...
```

Templates can also be found in example folder. 



#### 2. Load PES data file in and plot 2D PES

Click `Open...` button at up-right corner and select your PES data file. The PES will be showed in `plot window` immediately. The auto-generated plot may not be perfect for locating minima and saddle points. The users need to adjust the relevant parameters in `PES plot control` panel. 

<img src=".\Readme-figures\R3.png" alt="R3"  />

* **Max. V**: Maximum value in countour plot. Values larger than *Max. V* will be screened out. 
* **Min. V**: Minimum  value. Values smaller than *Mix. V* will be screened out (Don't adjust it or you will miss the local minimas).
* **Level**: Number of contour lines plotted on PES. 
* **Cmap**：Colormap styles.

Click `Regenrate` button you will see the new PES figure. If you mess the plot setting up, just click `Reset plot`. 



#### 3. Search minimum energy path

Firstly, users need to provide a initial guess string. An accurate initial guess string can be optimized to final result fast. The initial guess is defined by beads (at least 2 beads). Click `Guess beads` and provide the coordinates (X and Y) into dialog box,



<img src=".\Readme-figures\R4.png" alt="R4"  />

In this example, 4 beads are provided sequently to define a initial string. After clicking `OK`, the initial guess string is then plotted on PES in black solid line. 

<img src=".\Readme-figures\R5.png" alt="R5"  />

The program provides defaulf values for the optimization parameters. You can use them directly. If converge fail, you can adjust the parameters for the optimization. 

<img src=".\Readme-figures\R6.png" alt="R6"  />

* **No. of Beads**: Number of beads. It defines the the number of beads of the string. More beads more accuracy. 
* **Max. iter**: Maximum iteration number. If the optimization steps exceed the *Max. iter* value, the process will stop. 
* **Step size**:  *Step size* value detemines the gradient decend step-size.  



Click `Run` button. The optimization process will start. Then, the initial guess string is optimized to minimum energy path. The optimization process can be visualized in plot window. The  `Converged !` message in log panel means the optimization is successful. 



#### 4. Show results

Finally, click `Show` button in `MEP searching` panel. You will see the final results. 

 <img src=".\Readme-figures\R7.png" alt="R7"  />

Click `Export data` button, the beads' coordinates and relevant energies of MEP can be exported in a file for further use. 





## Tips

1. The initial guess beads will be updated to the latest optimized beads after one optimization process. Users can click run directly in the case of convergence failure. You need click `Guess beads` to generated new initial guess.
2. If the string vibrates, try to reduce the `step size` value.
3. If the beads on string move slowly,  try to increase the `step size` value.
4. Negative `step size` value yields *maximum energy path*



## Dependency

* pyqt5: 5.15
* Matplotlib: 3.1.3
* numpy: 1.15
* scipy:1.5.4



## License

MEPplot: A GUI program for plotting Minimal energy path on potential energy surface. 
Copyright (C)  2020 Xin Chen

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.


