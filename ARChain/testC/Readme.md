File with an input file close to the example from Mikkola and Merritt, 
"Implementating Few-Body Algorithmic Regularization with Post-Newtonian Terms," Astron. Jour. 135 (June 2008) 2398-2405.
Especially the three-body example below Eqn.~(72), SMBH + IMBH + star, see Figs.~(3) and (4).

My input file, test3bodiesC.in, 

```
0  3  0.005  15200.  0.e-3  0.0  1.0  1.d-99  0.0  77.26915  test3bodiesC.out  0  2  0.0  0.0  0.0  1.e-13  0  10000/IWR,N,DELTAT,TMAX,step,soft,cmet,Clight,outfile,Ixc,Nbh,spin,EPS,ivelocity,KSMX 
1.0           -1.8981e-4    0.0    0.0    0.0    -7.251137e-4    0.0 /m x y z vx vy vz 
1.0e-3        +0.18981e0    0.0    0.0    0.0    +0.72511378     0.0
2.857143e-6   +15.791955    0.0    0.0    0.0    +4.059612e-2    0.0
0  0  0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0  /STOP
```

And my G=1 units have U_m = 3.5e6 M_sol, U_l = 1.e-3 pc, so that U_t = 7.95309e6 s or 0.25201826 yrs.  This gives the speed-of-light
c = 77.2695027...  U_l/U_t .  Used the Python Astropy units package and especially the units.def_unit to handle these calculations.
The above input file is in these units.  Set the IMBH and the star at apoastron, on the plus x-direction, and the star orbits
the center of mass of the SMBH+IMBH system.

Nominal initial Keplerian orbital period are 0.19859 U_t for the IMBH and 142.1010 U_t for the star.

The IMBH seems to have merger at T = 14622.770000 U_t.  Oddly the output file behaves badly (for me) after that.  Sends the IMBH
to (x,y,z) = (1e9, 1e9, 1e9) as expected, but then DeltaT time step gets out of control, getting as bad as 44.0 and not the 
0.005 U_t that I originally set...could be some automated change to help speed things along though it ruins the plot of the
star orbit which I follow through the merger.


