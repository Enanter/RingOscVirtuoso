1Ghz Ring Oscillator with CMOS inverters.

# Introduction
In this project, the goal is designing a 1Ghz ring oscillator with CMOS inverters using the IBM 0.18um library on Cadence Virtuoso. 
To create a ring oscillator, odd numbers of stages of inverters are going to be used to create target frequency. Inverters' propagation delay is going to generate different output frequencies.
The relationship between frequency and propagation delay follows the formula:
Frequency = 2* Propagation delay*Number of inverters
# Methodology 
To configure propagation delay, understanding MOSFET dependencies is the key.

![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig1.png)

Figure 1. Equation for propagation delay from high to low on NMOS

![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig2.png)

Figure 2. Equation for propagation delay high to low on NMOS. 

The delay can be changed with different value of Vdd and (W/L)n on NMOS. PMOS has similar relationship with Vdd and (W/L)p.

# MOSFET design
3-stage inverters ring oscillator:
![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig3.png)
Figure 3. 3 stage inverters with Wn = 2u, Wp = 6u, and Vd =1.8v, a period was 0.204ns which is 4.9 Ghz.

![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig4.png)
Figure 4. 3 stage inverters with Wn = 2u, Wp = 6u, and Vd =1v, a period was 0.50706ns which is 1.9721 Ghz.

![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig5.png)
Figure 5. 3 stage inverters with Wn = 2u, Wp = 12u, and Vd =1.8v, a period was 0.0.24479ns which is 4.085 Ghz.

![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig6.png)
Figure 6. 3 stage inverters with Wn = 2u, Wp =10p, and Vd = 0.8V, a period is 1.01921ns which is 1.019 Ghz.

5-stage inverters ring oscillator:
![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig7.png)
Figure 7. 5 stage inverters with Wn = 2u, Wp = 6u, and Vd =1.8v, the period was 0.35333ns which is 2.83 Ghz.


# Layout design
3 stage inverter CMOS design has been choosen for the layout
![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig9.png)
Figure 8. 3 stage inverter CMOS ring oscillator that has Wp is 10 micrometers (width per finger is 5 micrometers with 2 fingers) and Wn is 2 micrometers (width per finger is 1 micrometer with 2 fingers). Supply voltage is 0.8 volt.
![alt text](https://github.com/Enanter/RingOscVirtuoso/blob/main/Docs_Pics/fig8.png)
Figure 9. The silicon layout with the IBM 180nm on Cadence Virtuoso.

# Conclusion
3 stage inverter has been used to reduce area. However, the ratio of (W/L)p / (W/L)n is 5, which is not optimal (the optimal ratio is 3.8). This may result it consumes higher energy than a 5 stages inverter design.
The output frequency is 1.019GhZ. It is within 2% error.

# Terms
 T_phl: propagation delay from high to low. When it is measured, it checks the when the output reaches 50% of Vdd.
 
 T_plh: propagation delay from low to high. When it is measured, it checks the when the output reaches 50% of Vdd.
 
 (W/L)n: width over length for NMOS.

 (W/L)p: width over length for PMOS.
 
 Vdd: Supply voltage.
 
 Vtn: Threshold voltage.

 µn: charge-carrier effective mobility.
 Cox: gate oxide capacitance per unit area.
 
