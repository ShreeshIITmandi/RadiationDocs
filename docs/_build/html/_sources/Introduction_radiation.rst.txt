Introduction to radiation
==========================
- Radiation heat transfer are commonly used to describe the science of the heat transfer caused by electromagnetic waves. Thermal radiation transfers the energy through electromagnetic waves so energy is transferred even when there is no medium.
- But there are some gases that actively participate in attenuating/augmenting of energy incident on it, such gases are called participating medium for example :math:`H_2O` and :math:`CO_2`.
- The intensity i.e, energy per unit steridian angle when passes through the participating medium. It experiences the following phenomena as shown in the figure below.

Radiation phenoemena
---------------------
- Absorption: Participating medium absorbs the energy from the incoming radiation which is a function of mole-fraction and temperature of the medium and attenuates the intensity.
- Emission: From Planck's radiation law any body at temperature highr then 0 K emits the radiation. Therefore the participating medium emits some energy which augments the intensity.
- In-scattering: Some medium which contains the particulate matter scatters the intensity. If the scattered intensity is in the direction of intensity then it augments the intensity.
- Out-scattering: If the scattered intensity is not in the direction of the travel of the intensity then it tries to attenutate the intensity :cite:p:`MODEST2013279`. 

 


.. figure:: radiationPhenomena.png
   :name: radiation
   :width: 1000px
   :height: 1000px
   :scale: 50 %
   :alt: alternate text
   :align: center
   
   Figure showing the intensity that is undergoing all the radiation phenomena.

Governing Equation
-------------------
Governing equation of the radiative transfer is obtained by conserving energy in the control volume due to all of the above phenomena and is represented by 
by the integro-differential radiative transfer equation (RTE) equation as shown below

.. math:: \frac{dI_{\eta}}{cdt} + \hat{s}\cdot \nabla I_{\eta}=\kappa_{\eta}I_{b\eta}-(\kappa_{\eta}+ \sigma_{s\eta})I_{\eta}+\frac{\sigma_{\eta}}{4\pi} \intop_{4\pi}I_{\eta}\left(\hat{s_{i}}\right)\Phi_{\eta}\left(\hat{s_i},\hat{s})\right)d\Omega_{i}
  :label: RTE
  
where

.. list-table::
   :widths: 25 25
   :header-rows: 1

   * - Symbols
     - Defintions
   * - .. math :: I_{\eta} 
     - Spectral intensity :math:`(W/(m^{3}-sr))`
   * - .. math :: I_{b\eta} 
     - Planck function :math:`(W/(m^{3}-sr))`
   * -  .. math :: n
     - Refractive index
   * -  .. math :: \beta_{\eta}=(\kappa_{\eta}+\sigma_{\eta}) 
     - Spectral extinction coefficient :math:`(m^{-1})`
   * - .. math :: \kappa_{\eta} 
     - Spectral absorption coeffcient :math:`(m^{-1})`
   * - .. math :: \sigma_{\eta}
     - Spectral scattering coeffcient :math:`(m^{-1})`
   * - .. math :: \omega_{\eta}
     - Spectral scattering albedo :math:`(m^{-1})`
   * - .. math :: c
     - speed of light 
     
**Note:** In the vast majority of engineering applications considered, local time is very small compared to the speed of light and the length scale, that the transient term :math:`\frac{dI}{dt}` is often neglected. But however, in the cases of laser application transient nature of the equation is used.


