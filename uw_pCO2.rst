.. _pCO2:

Underway |pCO2|
=========================================

PIs
  * Simone Alin (NOAA/PMEL)
Technicians
  * Julian Herndon (UW/NOAA/PMEL)
  * Andrew Collins (UW/NOAA/PMEL)

With assistance from Mr. Nick Benz (SIO-STS) to identify and clarify the source of MET data supplied by the ship; Mr. Royhon Agostine (SIO-STS) and Mr. Jake Pate (SIO-Revelle) to locate and identify the various scientific seawater supply systems aboard.

The partial pressure of carbon dioxide (|pCO2|) in the surface ocean was measured throughout the cruise track of this cruise with a General Oceanics 8050 |pCO2| Measuring System.
Uncontaminated seawater was continuously passed (~1.7-2.1 L/min) through a chamber where the seawater concentration of dissolved |CO2| was equilibrated with an overlaying headspace gas.
The |CO2| mole fraction of this headspace gas (|xCO2|) was measured every two minutes via a non-dispersive infrared analyzer (LiCor 7000) for 60 consecutive measurements.
At the end of these 60 discrete measurements, a set of five standard gases was analyzed; four of these standards have known |CO2| concentrations certified by the NOAA Earth Science Research Laboratory (ESRL) ranging from ~300 to ~900 ppm |CO2| (see Table 1).
The fifth standard is a tank of 99.9995% ultra-high purity nitrogen gas, used as a baseline 0% |CO2|.
Following the measurements of standard gases, six consecutive measurements of atmospheric |xCO2| were made of air supplied through tubing fastened to the ships forward jack staff.
Twice a day, the infrared analyzer was zeroed and spanned using the nitrogen gas and the highest concentration |CO2| standard (911.41 ppm).
In addition to measurements of seawater |xCO2|, atmospheric |xCO2|, and standard gases, other variables were monitored to evaluate system performance (e.g. gas and water flow rates, pump speeds, equilibrator pressures, etc.).
For more detail on the general design and operation of this underway |pCO2| system, see [Pierrot2009]_.

In coordination with Mr. John Ballard (ODF-SIO) and before departing from Guam, the |pCO2| system received maintenance by Andrew Collins and Julian Herndon.
We replaced the Nafion tubes, replumbed the ATM and EQU return lines (which were found to have been plumbed backwards), replaced the vent flow meter and added a filter upstream of it to help prolong its useful life, disassembled and cleaned the water flow meter which was stuck due to corrosion and salt build up inside the impeller housing.
The run routine was adjusted as described above and all the gas and water flows were adjusted.
The standard gases onboard were replaced with certified standards from ESRL; the existing standards had been sourced from Praxair.
The Resident Technicians onboard used bleach to clean/sanitize the scientific seawater system after we departed Guam and prior to the |pCO2| system being turned on.
Model and serial numbers for the |pCO2| instrument components and ancillary instruments have been recorded in a separate Excel file and will reported as part of the metadata that will accompany the final/processed |pCO2| data submission.
This |pCO2| system does not have a Druck or other external barometer installed in the dry box to measure the pressure in the LiCor cell.
The primary equilibrator in this |pCO2| system is an older, non-jacketed equilibrator built using a clear plastic filter housing.

Notes on seawater source and data:
------------------------------------------------

The |pCO2| system on this cruise was installed in the Hydrolab.
The R/V *Revelle* has three separate but related sources of uncontaminated underway seawater.
The first (#1) is fairly typical of her AGOR-24 sister ships like the R/V *Brown* and the R/V *Thompson* with an intake at the bow that feeds all the labs.
The second (#2) is sourced from the engine room sea-chest and is plumbed into the rest of the ship via a “T” in the system in the Hydrolab.
This system has a baffle/diaphragm pump to supply intake water for biologists concerned about damage to the organisms by the centrifugal pump used for system #1.
This (system #1) is the system that was used on this cruise.
The residence time of water in the engine room sea-chest is believed, by the Chief Engineer, to be less than a minute given the large volume of water taken from it to cool the engines.
There is no antifouling system installed in this engine room sea-chest.
The third (#3) system is an isolated/standalone flow-through at the bow, but separate from #1 at the bow.
System #3 has a TSG45 and SBE38, downstream and upstream respectively, of the centrifugal pump.
System #3 takes water in at the bow thruster and dumps it out over the side a few feet away.
This was an installation done in drydock to get around the modifications associated with installing the new bow thruster during the mid-life refurbishment.
The result is that the intake seawater temperature for system #1 and #2 comes from the independent system #3.
Salinity can be sourced either from system #3 or a separate TSG45 installed in the Hydrolab that is fed by either system #1 or #2.
System #1 (bow intake) does NOT have its own intake temperature probe.
System #2 (engine room sea-chest) does NOT have an intake temperature probe.
The |pCO2| system in the Hydrolab received water from system #2, intake temperature from system #3 and salinity data from the TSG45 in the Hydrolab, which measured salinity (along with temperature) of the source water from the sea-chest once it reached the Hydrolab.
The |pCO2| received water from a “T” before the sea-chest water was de-bubbled and subsequently fed to the TSG45.
To facilitate data processing and future troubleshooting of the *Revelle* |pCO2| system, the column headings for data in the |pCO2| files sourced from the ship are identified in Table 2.
Serial numbers and additional details for the instruments in table #2 are in a separate Excel file and will be reported as part of the metadata for |pCO2| data submitted for this cruise.

.. csv-table:: Table 1: Standard gases for P02W 2022 cruise UW |pCO2| system.
   :header: Standard	,Concentration (ppm),Tank Serial Numbers

   1,0.0,Praxair 5.0 Ultra High Purity N2
   2,283.42,LL55868
   3,399.51,LL127199
   4,539.97,LL127204
   5,911.41,LL127176

.. csv-table:: Table 2: |pCO2| system ship supplied data column headers for P02W 2022 cruise, Leg 1.  MWL = mean water level.
   :header: Column Header, Instrument, System, Location

   TSGF1,SW flow meter,3,Bow
   TSGT2,TSG45 temperature,2 and 3,Hydrolab
   TSGS2,TSG45 salinity,2 and 3,Hydrolab
   TSGF2,SW flow meter to TSG45,2 and 3,Hydrolab
   PCO2F,SW flow meter to |pCO2|,2 and 3,Hydrolab
   SST,SBE 38 temperature,3,Bow
   AT,RM Young temperature,MET,56’ above MWL*
   BP,RM Young barometer,MET,56’ above MWL*
   HDG,Konsberg GPS,,
   SOG,Speed over ground,,

While the raw data is not reported here, it has been collected and will be analyzed using MATLAB® routines developed by Dr. Denis Pierrot of the Atlantic Oceanographic and Meteorological Lab in Miami, FL.
Measurements of gas standards were generally within 1% of their certified value throughout the duration of the cruise.
During Leg 1 there were two separate, short periods where the instrument was not recording data.
The first time was as a result of a Windows 10 initiated update that restarted the computer and the second was the result of a loss of power due to a heavy load on the circuit used at the time.
In response, additional Windows updates were delayed until after the date of arrival in Hawaii, where an update will be run manually prior to Leg 2 to avoid a repeat situation.
The power loss has been addressed by changing the |pCO2| instrument power source to the ship’s clean power supplied by the UPS in the Main Lab.

The data from the |pCO2| system that is included as part of the ships data supplied by the onboard Resident Technicians to the Chief Scientist is |xCO2| (not |pCO2|) that has not been processed or evaluated for QA/QC and as such should be considered preliminary.


.. [Pierrot2009] Pierrot, D., Neill, C., Sullivan, K., Castle, R., Wanninkof, R.W., Lüger, H., Johannessen, T., Olsen, A., Feely, R.A., Cosca, C.E.;
    2009. Recommendations for autonomous underway pCO2 measuring systems and data-reduction routines. Deep-Sea Research II 56 (2009) 512–522 
