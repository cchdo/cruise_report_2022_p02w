
CTDO and Hydrographic Analysis
==============================

PIs
  * Todd Martz (SIO)
  * Susan Becker (SIO)
Technicians
  * Aaron Mau (SIO)

CTDO and Bottle Data Acquisition
--------------------------------

The CTD data acquisition system consisted of an SBE-11+ (V2) deck unit and a networked generic PC workstation running Windows 10.
SBE SeaSave7 v.7.26.7.121 software was used for data acquisition and to close bottles on the rosette.

CTD deployments were initiated by the console watch operators (CWO) after the ship had stopped on station.
The watch maintained a CTD cast log for each attempted cast containing a description of each deployment event and any problems encountered.

Once the deck watch had deployed the rosette, the winch operator would lower it to 20 meters.
The CTD sensor pumps were configured to start 10 seconds after the primary conductivity cell reports salt water in the cell.
The CWO checked the CTD data for proper sensor operation, waited for sensors to stabilize, and instructed the winch operator to bring the package to the surface in good weather or no more than 5 meters in high seas.
The winch was then instructed to lower the package to the initial target wire-out at no more than 60 m/min after 100 m depending on depth, sea-cable tension, and the sea state.

The CWO monitored the progress of the deployment and quality of the CTD data through interactive graphics and operational displays.
The altimeter channel, CTD pressure, wire-out and center multi-beam depth were all monitored to determine the distance of the package from the bottom.
The winch was directed to slow decent rate to 30 m/min 100 m from the bottom, and 20 m/min 50 m from the bottom.
The bottom of the CTD cast was usually to within 10-20 meters of the bottom determined by altimeter data.
For each full upcast, the winch operator was directed to stop the winch at up to 36 predetermined sampling pressures. During upcasts specific to bio sampling, the winch operator was directed to stop at up to 21 predetermined sampling pressures.
These standard depths were staggered every station using 3 sampling schemes.
The CTD CWO waited 30 seconds prior to tripping sample bottles, to ensure package had shed its wake.
An additional 15 seconds elapsed before moving to the next consecutive trip depth, which allowed for the SBE35RT to record bottle trip temperature averaged from 13 samples.

After the last bottle was closed, the CWO directed winch to recover the rosette.
Once the rosette was out of the water and on deck, the CWO terminated the data acquisition, turned off the deck unit and assisted with rosette sampling.

Additionally, the watch created a sample log for the deployment which recorded the depths bottles were tripped and correspondence between rosette bottles and analytical samples drawn.

The CTD sensors were rinsed after every cast using syringes of fresh water connected to Tygon tubing.
The tubing was left on the CTD between casts, with the temperature and conductivity sensors immersed in fresh water.

Each bottle on the rosette had a unique serial number, independent of the bottle position on the rosette.
Sampling for specific programs were outlined on sample log sheets prior to cast recovery or at the time of collection.
The bottles and rosette were examined before samples were drawn.
Any abnormalities were noted on the sample log, stored in the cruise database and reported in the APPENDIX.

CTDO Data Processing
--------------------

Shipboard CTD data processing was performed after deployment using SIO/ODF CTD processing software "ctdcal" v. 0.1.3b.
CTD acquisition data were copied onto a OS X system, and then processed.
CTD data at bottle trips were extracted, and a 2-decibar downcast pressure series created.
The pressure series data set was submitted for CTD data distribution after corrections outlined in the following sections were applied.

A total of |NSTA| CTD stations were occupied including one test station.
A total of |TCST| |PACK| casts were completed.

CTD data were examined at the completion of each deployment for clean corrected sensor response and any calibration shifts.
As bottle salinity and oxygen results became available, they were used to refine conductivity and oxygen sensor calibrations.

Temperature, salinity and, dissolved |O2| comparisons were made between down and upcasts as well as between groups of adjacent deployments.
Vertical sections of measured and derived properties from sensor data were checked for consistency.

A number of issues were encountered during |CRS| that directly impacted CTD analysis.
Issues that directly impacted bottle closures, such as slipping guide rings, were detailed in the Underwater Sampling Package section of this report.
Temperature, conductivity, and oxygen analytical sensor issues are detailed in the following respective sections.

Pressure Analysis
-----------------

Laboratory calibrations of CTD pressure sensors were performed prior to the cruise.
Dates of laboratory calibration are recorded on the underway sampling package table and calibration documents are provided in the APPENDIX.

The lab calibration coefficients provided on the calibration report were used to convert frequencies to pressure.
Initial SIO pressure lab calibration slope and offsets coefficients were applied to cast data.
A shipboard calibration offset was applied to the converted pressures during each cast.
These offsets were determined by the pre and post-cast on-deck pressure offsets.
The pressure offsets were applied per cast.

CTD #1281:

.. csv-table::
   :header: ,Start P (dbar),End P (dbar)

   Min,-0.20,-0.28
   Max,0.05,-0.08
   Average,0.09,-0.19

On-deck pressure reading varied from -0.20 to 0.05 dbar before the casts, and -0.28 to -0.08 dbar after the casts.
The pressure offset varied from -0.24 to 0.09, with a mean value of -0.1 dbar.

Temperature Analysis
--------------------

Laboratory calibrations of temperature sensors were performed prior to the cruise at the SIO Calibration Facility.
Dates of laboratory calibration are recorded on the underway sampling package table and calibration documents are provided in the APPENDIX.

The pre-cruise laboratory calibration coefficients were used to convert SBE3plus frequencies to ITS-90 temperature.
Additional shipboard calibrations were performed to correct systematic sensor bias.
Two independent metrics of calibration accuracy were used to determine sensor bias.
At each bottle closure, the primary and secondary temperature were compared with each other and with a SBE35RT reference temperature sensor.

The SBE35RT Digital Reversing Thermometer is an internally-recording temperature sensor that operates independently of the CTD.
The SBE35RT was located equidistant between the two SBE3plus temperature sensors.
The SBE35RT is triggered by the SBE32 carousel in response to a bottle closure.
According to the manufacturer’s specifications, the typical stability is 0.001 °C/year.
The SBE35RT was set to internally average over 13 samples, approximately a 15 second period.

A functioning SBE3plus sensor typically exhibit a consistent predictable well-modeled response.
The response model is second-order with respect to pressure and second-order with respect to temperature:


.. math::

  T_{cor} = T + cp_2 P^2 + cp_1 P + ct_2 T^2 + ct_1 T + c_0

Fit coefficients are shown in the following tables.

.. csv-table:: Primary temperature (T1) coefficients.
  :header: Station,:math:`cp_2`, :math:`cp_1`, :math:`ct_2`, :math:`ct_1`, :math:`c_0`

  1-8,9.127e-11,-7.1661e-7,0.0,0.0,4.7065e-4
  9-40,8.4036e-11,-8.6330e-7,0.0,0.0,1.1989e-3
  41-|LAST_STA|,-4.6532e-11,1.2251e-7,0.0,0.0,-8.1808e-4

.. csv-table:: Secondary temperature (T2) coefficients.
  :header: Station,:math:`cp_2`, :math:`cp_1`, :math:`ct_2`, :math:`ct_1`, :math:`c_0`

  1-8,0.0,-2.1424e-7,0.0,0.0,-1.4331e-4
  9-41,0.0,-8.1227e-8,0.0,0.0,-6.3841e-4
  42-|LAST_STA|,0.0,-1.3354e-7,0.0,0.0,-7.2422e-4

Corrected temperature differences are shown in the following figures.

.. 
  figure:: images/ctd_hydro_data_acq/reft-t1_vs_stn.*

  SBE35RT-T1 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/reft-t1_vs_stn_deep.*

  Deep SBE35RT-T1 by station (Pressure :math:`\geq` 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/reft-t2_vs_stn.*

  SBE35RT-T2 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/reft-t2_vs_stn_deep.*

  Deep SBE35RT-T2 by station (Pressure :math:`\geq` 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/t1-t2_vs_stn.*

  T1-T2 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/t1-t2_vs_stn_deep.*

  Deep T1-T2 versus station (Pressure :math:`\geq` 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/reft-t1_vs_p.*

  SBE35RT-T1 versus pressure.

.. 
  figure:: images/ctd_hydro_data_acq/reft-t2_vs_p.*

  SBE35RT-T2 versus pressure.

.. 
  figure:: images/ctd_hydro_data_acq/t1-t2_vs_p.*

  T1-T2 versus pressure.

The 95% confidence limits for the mean low-gradient (values -0.002 °C :math:`\leq` T1-T2 :math:`\leq` 0.002 °C) differences are ±0.00391 °C for SBE35RT-T1, ±0.00387 °C for SBE35RT-T2 and ±0.00157 °C for T1-T2.
The 95% confidence limits for the deep temperature residuals (where pressure :math:`\geq` 2000 dbar) are ±0.00087 °C for SBE35RT-T1, ±0.00099 °C for SBE35RT-T2 and ±0.00087 °C for T1-T2.

Problems arose during the |CRS| cruise, prompting the SBE3 sensors to be exchanged.
  * While deploying during station 9, cables to the deck box were loose. This was misdiagnosed as a sensor problem and was deployed without a secondary sensor on cast 4.
  * Differences in primary and secondary SBE3 were abnormally large during the pre-cast soak following station 32 and the sensors were exchanged during stations 40 and 41 to troubleshoot.

Minor complications impacted the reference temperature sensor data.
  * Internal memory overflowed following station 9 and data was not captured during stations 10 and 11.
  * During casts designated for bio, many bottles were fired at the surface and sometimes were too fast (< 15 seconds) for a reading.

The resulting affected sections of data have been coded and documented in the quality code APPENDIX.

Conductivity Analysis
---------------------

Laboratory calibrations of conductivity sensors were performed prior to the cruise at the Sea-Bird Calibration Facility.
Dates of laboratory calibration are recorded on the underway sampling package table and calibration documents are provided in the APPENDIX.

The pre-cruise laboratory calibration coefficients were used to convert SBE4C frequencies to mS/cm conductivity values.
Additional shipboard calibrations were performed to correct sensor bias.
Corrections for both pressure and temperature sensors were finalized before analyzing conductivity differences.
Two independent metrics of calibration accuracy were examined.
At each bottle closure, the primary and secondary conductivity were compared with each other.
Each sensor was also compared to conductivity calculated from check sample salinities using CTD pressure and temperature.

The differences between primary and secondary temperature sensors were used as filtering criteria to reduce the contamination of conductivity comparisons by package wake.
The coherence of this relationship is shown in the following figures.

.. 
  figure:: images/ctd_hydro_data_acq/c_t_coherence.*

  Coherence of conductivity differences as a function of temperature differences.

.. 
  figure:: images/ctd_hydro_data_acq/refc-c1_vs_stn.*

  Corrected C\ :sub:`Bottle` - C1 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/refc-c1_vs_stn_deep.*

  Deep Corrected C\ :sub:`Bottle` - C1 versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/refc-c2_vs_stn.*

  Corrected C\ :sub:`Bottle` - C2 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/refc-c2_vs_stn_deep.*

  Deep Corrected C\ :sub:`Bottle` - C2 versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/c1-c2_vs_stn.*

  Corrected C1-C2 versus station.

.. 
  figure:: images/ctd_hydro_data_acq/c1-c2_vs_stn_deep.*

  Deep Corrected C1-C2 versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/refc-c1_vs_p.*

  Corrected C\ :sub:`Bottle` - C1 versus pressure.

.. 
  figure:: images/ctd_hydro_data_acq/refc-c2_vs_p.*

  Corrected C\ :sub:`Bottle` - C2 versus pressure.

.. 
  figure:: images/ctd_hydro_data_acq/c1-c2_vs_p.*

  Corrected C1-C2 versus pressure.

A functioning SBE4C sensor typically exhibit a predictable modeled response.
Offsets for each C sensor were determined using C\ :sub:`Bottle` - C\ :sub:`CTD` differences in a deeper pressure range (500 or more dbars).
After conductivity offsets were applied to all casts, response to pressure, temperature and conductivity were examined for each conductivity sensor.
The response model is second-order with respect to pressure, second-order with respect to temperature, and second-order with respect to conductivity:

.. math::

  C_{cor} = C + cp_2 P^2 + cp_1 P + ct_2 T^2 + ct_1 T + cc_2 C^2 + cc_1 C + \text{Offset}

Fit coefficients are shown in the following tables.

.. csv-table:: Primary conductivity (C1) coefficients.
  :header: Station, :math:`cp_2`, :math:`cp_1`, :math:`ct_2`, :math:`ct_1`, :math:`cc_2`, :math:`cc_1`, :math:`c_0`

  |FIRST_STA|-|LAST_STA|,2.2312e-10,-1.7838e-6,0.0,-3.7387e-4,0.0,0.0,1.4153e-3

.. csv-table:: Secondary conductivity (C2) coefficients.
  :header: Station, :math:`cp_2`, :math:`cp_1`, :math:`ct_2`, :math:`ct_1`, :math:`cc_2`, :math:`cc_1`, :math:`c_0`

  |FIRST_STA|-|LAST_STA|,1.6912e-10,-1.3829e-6,0.0,0.0,0.0,-3.2935e-4,1.3273e-2

Salinity residuals after applying shipboard P/T/C corrections are summarized in the following figures.
Only CTD and bottle salinity data with "acceptable" quality codes are included in the differences.
Quality codes and comments are published in the APPENDIX of this report.

.. 
  figure:: images/ctd_hydro_data_acq/btlsal-sal_vs_stn.*

  Salinity residuals versus station.

.. 
  figure:: images/ctd_hydro_data_acq/btlsal-sal_vs_stn_deep.*

  Deep Salinity residuals versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/btlsal-sal_vs_p.*

  Salinity residuals versus pressure.

The 95% confidence limits for the mean low-gradient (values -0.002 ºC :math:`\leq` T1-T2 :math:`\leq` 0.002 ºC) differences are ±0.00512 mPSU for salinity-C1SAL.
The 95% confidence limits for the deep salinity residuals (where pressure :math:`\geq` 2000 dbar) are ±0.00158 mPSU for salinity-C1SAL.

Minimal issues affected conductivity and calculated CTD salinities during this cruise.
  * Bottle stops in halocline may have had insufficient stop time during some casts, leading to low-biased measurements.

The resulting affected sections of data have been coded and documented in the quality code APPENDIX.

CTD Dissolved Oxygen (SBE43)
----------------------------

Laboratory calibrations of the dissolved oxygen sensors were performed prior to the cruise at the SBE calibration facility.
Dates of laboratory calibration are recorded on the underway sampling package table and calibration documents are provided in the APPENDIX.

The pre-cruise laboratory calibration coefficients were used to convert SBE43 frequencies to µmol/kg oxygen values for acquisition only.
Additional shipboard fitting were performed to correct for the sensors non-linear response.
Corrections for pressure, temperature, and conductivity sensors were finalized before analyzing dissolved oxygen data.
Corrections for hysteresis are applied following Sea-Bird Application Note 64-3.
The SBE43 sensor data were compared to dissolved |O2| check samples taken at bottle stops by matching the downcast CTD data to the upcast trip locations along isopycnal surfaces.
CTD dissolved |O2| was then calculated using Clark Cell MPOD |O2| sensor response model for Beckman/SensorMedics and SBE43 dissolved |O2| sensors.
The residual differences of bottle check value versus CTD dissolved |O2| values are minimized by optimizing the PMEL DO sensor response model coefficients using the BFGS non-linear least-squares fitting procedure.

The general form of the PMEL DO sensor response model equation for Clark cells follows Brown and Morrison [Mill82]_ and Owens [Owen85]_.
Dissolved |O2| concentration is then calculated:


.. math::
  O_2 = S_{oc} \cdot (V + V_{\textrm{off}} + \tau_{20} \cdot e^{(D_1 \cdot p + D_2 \cdot (T - 20))} \cdot dV/dt) \cdot O_{sat} \cdot e^{T_{cor} \cdot T} \cdot e^{[(E \cdot p) / (273.15 + T)]}

Where:

- V is oxygen voltage (V)
- D\ :sub:`1` and D\ :sub:`2` are (fixed) SBE calibration coefficients
- T is corrected CTD temperature (°C)
- p is corrected CTD pressure (dbar)
- dV/dt is the time-derivative of voltage (V/s)
- O\ :sub:`sat` is oxygen saturation
- S\ :sub:`oc`, V\ :sub:`off`, :math:`\tau`\ :sub:`20`, T\ :sub:`cor`, and E are fit coefficients

All stations were fit together to get an initial coefficient estimate.
Stations were then fit individually to refine the coefficients as the membrane does not deform the same way with each cast.
If the fit of the individual cast had worse resdiuals than the group, they were reverted to the original group fit coefficients.

.. csv-table doesn't work with these directives for some reason?

.. table:: SBE43 group fit coefficients. Coefficients were further refined station-by-station.

  ======= ============ ============= ======================= ============= ============
  Station S\ :sub:`oc` V\ :sub:`off` :math:`\tau`\ :sub:`20` T\ :sub:`cor` E
  ======= ============ ============= ======================= ============= ============
  |FIRST_STA|-|LAST_STA|  4.7574e-1    -5.0079e-1    1.56                    -3.1680e-4    3.754e-2
  ======= ============ ============= ======================= ============= ============

CTD dissolved |O2| residuals are shown in the following figures :ref:`Oxy-lograd` through :ref:`Oxy-deep`.

.. _Oxy-lograd:

.. 
  figure:: images/ctd_hydro_data_acq/oxy-43_vs_stn.*

  |O2| residuals versus station.

.. _Oxy-deep:

.. 
  figure:: images/ctd_hydro_data_acq/oxy-43_vs_stn_deep.*

  Deep |O2| residuals versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/oxy-43_vs_p.*

  |O2| residuals versus pressure.

The 95% confidence limits of 1.71 (µmol/kg) for all acceptable (flag 2) dissolved oxygen bottle data values and 1.52 (µmol/kg) for deep dissolved oxygen values are only presented as general indicators of the goodness of fit.
CLIVAR GO-SHIP standards for CTD dissolved oxygen data are < 1% accuracy against on board Winkler titrated dissolved |O2| lab measurements.

Issues arose with the acquisition and processing of CTD dissolved oxygen data.
  * SBE43 data appeared noisy at depths exceeding 800 m following a biofouling event during station 32. Sensors were replaced at stations 32 and 94 in an attempt to alleviate the noise, which gradually dissapated by station 101.


CTD Dissolved Oxygen (RINKO)
----------------------------

A two-point calibration was performed prior and after deployment on the rosette.
These calibrations produced sets of calibration coefficients (G and H) to adjust factory calibration of dissolved oxygen raw voltage.
The calibrations also provided an assessment of foil degradation over the course of the 90 stations.
As per manufacturer (JFE Advantech Co., Ltd.) recommendation, 100% saturation points were obtained via bubbling ambient air in a stirred beaker of tap water about 30 minutes, removing air stone, then submersing the powered Rinko.
Zero point calibrations also followed general manufacturer recommendations, using a sodium sulfite solution (25g in 500mL deionized water).
Dissolved oxygen raw voltage (DOout), atmospheric pressure, and solution temperature were recorded for calculation of new oxygen sensor coefficients (G and H).

Rinko temperature (factory coefficients) was used for pre-cruise calibration.
Generally, the Rinko III sensor appears to have performed as expected with no major problems or sharp drift throughout the deployment.
An SBE 43 dissolved oxygen sensor was deployed simultaneously.
Both oxygen sensor data sets were analyzed and quality controlled with Winkler bottle oxygen data.
RinkoIII data used as primary oxygen for all stations (|FIRST_STA|-|LAST_STA|), excluding stations 10-12 when the RINKO cable needed to be changed.

RINKO data was acquired, converted from volts to oxygen saturation, and then multipled by the oxygen solubility to find values in µmol/kg.
The resulting data were then fitted using the equations developed by [Uchida08]_:

.. math::
  [O_2] = (V_0 / V_c - 1) / K_{sv}
.. math::
  K_{sv} = c_0 + c_1 T + c_2 T^2, \hspace{6pt} V_0 = 1 + d_0 T, \hspace{6pt} V_c = d_1 + d_2 V_r

where:

- T is temperature (ºC)
- V\ :sub:`r` is raw voltage (V)
- V\ :sub:`0` is voltage at zero |O2| (V)
- c\ :sub:`0`, c\ :sub:`1`, c\ :sub:`2`, d\ :sub:`0`, d\ :sub:`1`, d\ :sub:`2` are calibration coefficients

Oxygen is further corrected for pressure effects:

.. math::
  [O_2]_c = [O_2] (1 + c_p P / 1000) ^ {1/3}

where:

- P is pressure (dbar)
- c\ :sub:`p` is pressure compensation coefficient

Lastly, salinity corrections are applied [GarciaGordon1992]_:

.. math::
  [O_2]_{sc} = [O_2]_c \exp[{S (B_0 + B_1 T_S + B_2 T_S^2 + B_3 T_S^3) + C_0 S^2}]

where:

- T\ :sub:`S` is scaled temperature (T\ :sub:`S` = ln[(298.15 – T)/(273.15 + T)])
- B\ :sub:`0`, B\ :sub:`1`, B\ :sub:`2`, B\ :sub:`3`, C\ :sub:`0` are solubility coefficients

All stations excluding 10-12 were fit together to get an initial coefficient estimate.
Stations were then fit in groups of similar profiles to get a further refined estimate.
Individual casts were then fit to remove the noticeable time drift in coefficients
If the fit of the individual cast had worse resdiuals than the group, they were reverted to the original group fit coefficients.

.. csv-table:: Rinko group fit coefficients. Coefficients were further refined station-by-station.
  :header: Station, :math:`c_0`, :math:`c_1`, :math:`c_2`, :math:`d_0`, :math:`d_1`, :math:`d_2`, :math:`c_p`

  1-9,1.8834,2.7106e-2,7.5022e-4,5.1571e-4,-1.9373e-1,3.0792e-1,8.7822e-2
  10-12,1.8612,2.9074e-2,9.2059e-4,2.4233e-3,-1.9987e-1,3.1466e-1,9.7739e-2
  13-|LAST_STA|,1.8783,4.8992e-2,2.2758e-4,2.9361e-3,-1.8483e-1,2.9822e-1,6.7778e-2

CTD dissolved |O2| residuals are shown in the following figures.

.. 
  figure:: images/ctd_hydro_data_acq/oxy-rinko_vs_stn.*

  |O2| residuals versus station.

.. 
  figure:: images/ctd_hydro_data_acq/oxy-rinko_vs_stn_deep.*

  Deep |O2| residuals versus station (Pressure >= 2000dbar).

.. 
  figure:: images/ctd_hydro_data_acq/oxy-rinko_vs_p.*

  |O2| residuals versus pressure.

The 95% confidence limits of 1.27 (µmol/kg) for all acceptable (flag 2) dissolved oxygen bottle data values and 0.58 (µmol/kg) for deep dissolved oxygen values are only presented as general indicators of the goodness of fit.
CLIVAR GO-SHIP standards for CTD dissolved oxygen data are < 1% accuracy against on board Winkler titrated dissolved |O2| lab measurements.

Issues arose with the RINKO between stations 10-12.
* During 10, the RINKO upcast and downcast displayed abnormal voltages, prompting us to exchange sensor serial 0296 for 0251.
* During 11-12, the RINKO voltage routinely spiked to 0. This was resolved by exchanging the RINKO cable connecting it to the CTD.

.. [Mill82] Millard, R. C., Jr., “CTD calibration and data processing techniques at WHOI using the practical
   salinity scale,” Proc. Int. STD Conference and Workshop, p. 19, Mar. Tech. Soc., La Jolla, Ca.
   (1982).

.. [Owen85] Owens, W. B. and Millard, R. C., Jr., “A new algorithm for CTD oxygen calibration,” Journ. of Am.
   Meteorological Soc., 15, p. 621 (1985).

.. [Uchida08] Uchida, H., Kawano, T., Kaneko, I., Fukasawa, M. "In Situ Calibration of Optode-Based Oxygen Sensors," J. Atmos. Oceanic Technol.,
    2271-2281, (2008)

.. [GarciaGordon1992] García, H. E., and L. I. Gordon, 1992: Oxygen solubility in sea- water: Better fitting equations. Limnol. Oceanogr., 37, 1307– 1312.