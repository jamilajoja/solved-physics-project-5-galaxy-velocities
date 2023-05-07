Download Link: https://assignmentchef.com/product/solved-physics-project-5-galaxy-velocities
<br>



Our model of the Universe is that it is an infinite space filled with a uniform “gas” of galaxies. To a first approximation we can think of these galaxies as moving in random directions with each component of the velocity being drawn from a Gaussian distribution (surprise!) centered on zero (so each component has an equal chance of being positive or negative) with some standard deviation <em>σ<sub>v</sub></em>. Our goal in this project is to determine <em>σ<sub>v</sub></em>.

We measure galaxy velocities by measuring the shift in the spectral lines of a galaxy from the wavelengths we expect, called the redshift <em>z</em>, a dimensionless quantity that can be measured very accurately. The speed of light times this redshift, <em>cz</em>, gives us the velocity at which the galaxy appears to be moving away or toward us, usually expressed in km/sec. However, the redshift is actually a combination of the doppler shift, due to the galaxy’s motion, which is what we want, and a cosmological redshift due to the light having travelled through an expanding of the Universe. Hubble’s law tells us that the part of the velocity due to the cosmological redshift is given by <em>H</em><sub>0</sub><em>r</em>, where <em>r </em>is the distance in megaparsecs (Mpc) (an Mpc is about 3 million light years) and <em>H</em><sub>0 </sub>= 70km/sec/Mpc is Hubble’s constant. Thus if we can measure the redshift <em>z </em>and the distance <em>r </em>we can obtain the radial velocity via

<em>v </em>= <em>cz </em>− <em>H</em><sub>0</sub><em>r                                                                                                             </em>(1)

Now, it turns out that measuring distance is difficult, and the uncertainty in distance measurements is 5-15%. For distant galaxies, where <em>H</em><sub>0</sub><em>r &gt;&gt; v</em>, this introduces crazy large uncertainties in the radial velocity. For example, suppose we measure the distance of a galaxy to be 100Mpc with an uncertainty of 10Mpc. Since <em>r </em>is multiplied by <em>H</em><sub>0 </sub>in the formula, this translates into an uncertainty of 700km/sec in the velocity. Given that velocities of galaxies are typically around a few hundred km/sec, this means that the uncertainty in velocity can be greater than the velocity itself! Thus galaxy velocity data is typically only useful when you have many measurements that you can combine to reduce the uncertainty.

Note that we can only measure the radial velocity of a galaxy, i.e. it’s motion toward or away from us. For galaxies in different directions this will be a different component of the velocity vector <em>~v</em>, but since we have good evidence that the Universe is <em>isotropic </em>(the same in all directions), then we should be able to treat the radial component of velocity the same as if it were the <em>x</em>, <em>y</em>, or <em>z </em>component. In other words, we would expect the radial component of velocity to be drawn from a Gaussian distribution centered on zero with standard deviation <em>σ<sub>v</sub></em>.

On the course Canvas site you will find the files galvel.dat and grpvel.dat, which contain galaxy velocities and galaxy group velocities respectively. You will be using the 1st and 2nd columns of these files, which are measured radial velocity of the <em>i</em>th galaxy, <em>v<sub>i</sub></em>, and its measurement uncertainty <em>σ<sub>i</sub></em>, both of which are in units of km/sec. Galaxies with positive velocities are moving toward us and those with negative velocities are moving away from us. We can model each measured radial velocity as the sum of the actual velocity <em>u<sub>i </sub></em>of the galaxy plus some noise,, where the noise <em><sub>i </sub></em>is drawn from a Gaussian distributions with standard deviation <em>σ<sub>i </sub></em>and the actual velocity <em>u<sub>i </sub></em>is drawn from a Gaussian distribution with standard deviation <em>σ<sub>v</sub></em>. Thus the measured velocity <em>v<sub>i </sub></em>is drawn from a Gaussian

distribution centered on zero with standard deviation given by <sup>p</sup><em>σ<sub>v</sub></em><sup>2 </sup>+ <em>σ<sub>i</sub></em><sup>2</sup>.

The problem of estimating <em>σ<sub>v </sub></em>is thus very similar to the problem of estimating the standard deviation of a set of numbers, with the differences that 1) we already know that the “true” average is zero, and 2) we need to account for the measurement uncertainty for each velocity. You should be able to convince yourself that the likelihood function for <em>σ<sub>v </sub></em>is

(2)

where we absorbed all the constants into <em>A</em>. Unfortunately, it’s too messy to find the maximum likelihood by taking

a derivative, so we will instead just plot the likelihood vs. <em>σ<sub>v </sub></em>and find the maximum likelihood value that way.

One complication for a large data set is that the product in the formula above can get so small that the computer will round it to zero. One solution is to calculate the log likelihood instead,

(3)

2

where <em>C </em>is a constant. First calculate ln<em>L </em>with <em>C </em>= 0 and find where the maximum occurs. This is your maximum likelihood value for <em>σ<sub>v</sub></em>. To plot the likelihood, choose <em>C </em>to be the negative of the maximum value of the ln<em>L</em>, so that the maximum value of ln<em>L </em>becomes zero. Then you can plot the Likelihood using this value of <em>C </em>and the likelihood at the peak will be 1. You can find the uncertainty in <em>σ<sub>v </sub></em>by fitting a Gaussian to the Likelihood peak and determining the width of the peak from the standard deviation of the Gaussian.

Now, in principle groups of galaxies should have a smaller <em>σ<sub>v </sub></em>than individual galaxies since their velocities are essentially averages of the velocities of their constituent galaxies. From your estimates of <em>σ<sub>v </sub></em>for the two datasets, calculate a confidence level that the two datasets have a different <em>σ<sub>v</sub></em>.

Finally, we can ask the question of how good our model is at describing the data. From the discussion above, the

quantities <em>v<sub>i</sub>/</em><sup>p</sup><em>σ<sub>v</sub></em><sup>2 </sup>+ <em>σ<sub>i</sub></em><sup>2 </sup>should be drawn from a Gaussian distribution centered on zero with a standard deviation of 1. Using your maximum likelihood value of <em>σ<sub>v</sub></em><sup>2</sup>, make a histogram of these values for both datasets. Plot on top of your histogram a Gaussian centered on zero with standard deviation of 1.

Give your result for <em>σ<sub>v </sub></em>for each dataset together with its uncertainties. A good name for <em>σ<sub>v </sub></em>is the velocity dispersion, which here means the spread of velocity values. Discuss how confidently you can say that the <em>σ<sub>v </sub></em>of the two data sets is different. To calculate this, find the standard deviation of the difference of the two values and determine how many standard deviations your value is from zero. Discuss how well the Gaussian model describes the data, i.e. how well does your histogram match a Gaussian centered on zero with a standard deviation of 1. If it doesn’t match, discuss possible reasons for the failure of the model. For example, galaxies falling into clusters of galaxies will have unexpectedly large velocities. Do you see evidence for these nonGaussian tails in your histogram?


