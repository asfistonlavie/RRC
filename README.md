# RRC
<b>Drosophila melanogaster Recombination Rate Calculator (RRC) in </i>Drosophila melanogaster</i></b>

Recombination rates are often estimated based on the relationship between the physical and genetic maps of the Drosophila genome.  Early recombination estimates, such as the adjusted coefficient of exchange (Kindahl 1994) were based on cytological markers in combination with DNA content estimates from optical densities of polytene chromosomes (Sorsa 1988).  Other techniques such as R TE (Hey and Kliman 2002) use transposable elements as markers on the physical map (Ising and Block 1984). However, with the availability of the whole genome sequence of, the physical map of the genome is much more precise, which facilitates more accurate estimation of recombination rates in D.melanogaster (Hey and Kliman 2002; Marais et al. 2001).

Recombination rates are now estimated by plotting Marey maps of the genetic positions of molecular markers (in centimorgans, cM) against their physical position (in Megabase pairs, Mbp). The recombination rate at any given nucleotide coordinate is estimated by taking the slope of the curve relating the genetic to the physical maps in one of two ways. One could employ a sliding window approach, in which a linear function is used to fit the genetic position as a function of physical position within a window of a given size along a chromosome arm.  With this approach, the slope of this linear function within the window is taken as local recombination rate.  Alternatively, the genetic position of the markers can be mapped as a function of physical position using an nth degree polynomial curve across an entire chromosome arm.  Under this approach, recombination is estimated at an individual nucleotide coordinate as the derivative of the nth degree polynomial curve.  While the polynomial curve approach is less sensitive to regional variation in recombination rates than the sliding window approach, it is more robust to errors in the physical and genetic maps.

In order to correct the recombination rate calculated for the telomere and centromere regions which can be biased, we start from each telomere and fit the data with the 3rd order polynomial with an increasing number of points starting from the telomere. The R-squared starts off close to 1 but at some points goes down precipitously. That is the point at which we define the telomere/non-telomere transition. In most cases, the estimates of the recombination rate for the telomereic region are close to zero and so we just define telomeric recombination rate to be zero. For the centromeric regions, we define the transition to a zero recombination rate at the point for which the recombination rate estimate based on the 3rd degree polynomial becomes negative. Then, we recalculated the regression for each chromosome arm without the two extremity regions defined. The differences of the R-squared for all the points and using only the points outside of telemoric and centromeric regions are not substantial. To give you an example with the 2R chromosome, the R-squared for all points is equal to 0.9929 and for the points outside telomeres and centromeres it is 0.9916. This last step allows to re-ajusted the recombination rates to the recombination rates experimentally observed into the telomere and centromere regions.

We selected 655 genes that have been localized on both the physical and genetic maps of Release 5.36 of the D. melanogaster genome from Flybase. Using these genes as markers, we plotted Marey maps (see below) for each of the five chromosome arms with detectable recombination (2R, 2L, 3L, 3R, and X). Recombination is thought to be absent or negligible on the fourth chromosome. After removing outliers, we ended up with 618 selected genes. We fit a third-order polynomial curve to the genetic map position as a function of physical position for the remaining markers on each chromosome arm (n = 110, 101, 82, 160, and 165 genes for chromosome arms 2L, 2R, 3L, 3R and X, respectively). The fit for all chromosome arms is quite good with R2 mean and median of 0.99.

We estimate recombination as the derivative of this 3rd order polynomial curve at a given nucleotide coordinate. For any locus, this web tool estimates recombination at the start coordinate, end coordinate, as well as the midpoint of the locus. Because of the smoothing effect of this recombination estimation technique, there will be little difference in the recombination rate estimates at these three points for small loci. However, we provide all three estimations in the event that the locus of interest is sufficiently large for regional variation in recombination rate.

<b>How to cite the RRC</b>
- Fiston-Lavier AS and Petrov DA. Drosophila melanogaster Recombination Rate Calculator: http://petrov.stanford.edu/cgi-bin/recombination-rates_updateR5.pl
- Fiston-Lavier AS*, Singh ND*, Lipatov M, and Petrov DA. Drosophila melanogaster recombination rate calculator. 2010. Gene. doi:10.1016/j.gene.2010.04.015
- Singh ND, Arndt PF, and Petrov DA. Genomic Heterogeneity of Background Substitutional Patterns in Drosophila melanogaster. 2005. Genetics 169, 709-722.
