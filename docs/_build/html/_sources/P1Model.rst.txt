P1 model for radiation
=========================
In order to solve the complex integro-differential RTE :math:numref:`RTE` equation, the method of spherical harmonics can be used to convert the equation to simple partial differential equations. This method is mostly videly used in the combustion community simply for the fact that it helps in accurate prediction of temperature.

General formulation of P1 approximation
---------------------------------------
.. math:: I(s,\hat{s})=\sum_{l=0}^{\infty} \sum_{m=-l}^l I_l^m(r)Y_l^m(\hat{s})

where,

:math:`Y^m_l(\hat{s})` is the Legendre polynomial in direction and :math:`s` is the location inside the medium.

 

For P1 approximation l=1

.. math:: I(s,\hat{s})= I_{0}^{0}Y_0^0 + I_1^{-1}Y_1^{-1}+I_0^0Y_1^0+I_1^1Y_1^1
   
After simplification the above equation is simplified to (for detailed derivation please refer :cite:p:`Modest16`)

.. math:: I(s,\hat{s})=a(s)+b(s).\hat{s}


.. math :: I(s,\hat{s}) = \frac{G(s) + 3Q(s) · \hat{s}}{4π}


where 

 G(s)= Total irradiation

 Q(s)= Total heat flux
 
and is given by

.. math:: \nabla \cdot Q=(1-\omega)(4\pi I_b-G)

and

.. math:: \nabla G=-(3-A_1\omega)q

Combining above two equations results in solving general Helmholtz equation in G 

.. math:: \nabla(\Gamma\nabla G)-\kappa G=-(1-\omega)4\kappa \pi I_b


where,

.. list-table:: 
   :widths: 25 25
   :header-rows: 1

   * - Symbols
     - Defintions
   * - .. math :: \Gamma
     - .. math :: \frac{1}{3\times(\kappa+\omega)-A_1 \times\omega}
   * - .. math :: I_{b}
     - Planck function
   * -  .. math :: n
     - Refractive index
   * -  .. math :: A_1
     - Scattering phase function
   * - .. math :: \omega
     - Scattering albedo

Boundary Condition 
-------------------
The basic energy conservation on the wall yields that heat flux form the opaque wall is equal to sum of the energy emitted and reflected form the surface. Which is expressed as

.. math:: 2q\cdot \hat{n} = 4j_w-G=\frac{\epsilon}{2-\epsilon}\times(4 \pi I_{bw}-G) 


which after simplification will result in

.. math :: -\frac{2-\epsilon}{\epsilon}\frac{2}{3-A_1\omega}\hat{n}.\nabla G+G=4 \pi I_{bw}


.. list-table:: 
   :widths: 25 25
   :header-rows: 1

   * - Symbols
     - Defintions
   * - .. math :: \epsilon
     - Wall emissivity
   * - .. math :: I_{bw}
     - Planck function
   * -  .. math :: T_w
     - Wall temperature
     
     
Limitation of the method
------------------------
This method is applicable mostly for optical thick case i.e, :math:`\kappa \times L_c>1` where :math:`L_c` is the characteristic length of the geometry.

- In the application like micro-combustor and micro-channnels where in the characterstic lenghts are small, this model fails to predict.

- In the application wherein the absorption coefficients are low i.e, in the case of absorption coeffcient of the medium at very high temperature and low mole fraction of the participating gas this model does'nt accurately predict.

Dicretisation of P1 Governing equation
--------------------------------------
The governing equation for P1 when discretised using central difference gives the following set of equation for each grid point considered

.. math:: G(i,j,k)\left(-\frac{2 \Gamma}{\Delta x^2}-\frac{2 \Gamma}{\Delta y^2}-\frac{2 \Gamma}{\Delta z^2} \right) + \Gamma \left(\frac{G(i+1,j,k)+G(i-1,j,k)}{\Delta x^2} \right)+\\ \Gamma\left( \frac{G(i,j+1,k)+G(i,j-1,k)}{\Delta y^2}+\frac{G(i,j,k+1)+G(i,j,k-1)}{\Delta z^2}\right) \\ \\ = -(1-\omega)4\kappa\sigma T^4(i,j,k)

**At the boundary**

Showing discretisation only on one boundary 

.. math:: G(i,j,k)\left(1-\frac{2}{\Delta x}\frac{2-\epsilon}{\epsilon}\frac{2}{3-A_1\omega}\right)+\left(\frac{2}{\Delta x}\frac{2-\epsilon}{\epsilon}\frac{2}{3-A_1\omega}\right) G(i-1,j,k)=4\sigma T^4_w


So the above discretisation will lead to formulation of 

.. math:: Ax=b
