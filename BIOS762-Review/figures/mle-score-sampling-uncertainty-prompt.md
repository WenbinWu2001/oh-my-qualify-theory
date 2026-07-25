Create a self-contained Python 3 script using NumPy and Matplotlib that produces a publication-quality schematic figure explaining the relationship between the score, log-likelihood curvature, and Fisher information in one-parameter maximum likelihood estimation.

Use the scalar normal-location model X_i iid~N(xi_*,1), with xi_*=0. Work with the total log-likelihood and total score, not their averages. Up to an additive constant,

ell_n(xi)-ell_n(xi_hat) = -(n/2)(xi-xi_hat)^2,
xi_hat = X_bar,
U_n(xi) = ell_n'(xi) = n(X_bar-xi),

so U_n(xi_*)~N(0,n), -ell_n''(xi)=n, and I_1(xi_*)=1.

Construct a 2-row by 3-column figure. The top row uses n=8 and the bottom row uses n=80.

LEFT COLUMN — ONE REALIZATION:
For each n, use xi_hat=xi_*+0.8/sqrt(n). Plot the centered total log-likelihood as a solid blue curve. Draw a red dashed vertical line at xi_*=0 and make the xi_*=0 tick label red. Draw a dark-blue dotted vertical line at xi_hat, a dark-blue dot at the maximum, and label it xi_hat. At xi_*, draw a thin yellow-brown tangent whose slope equals U_n(xi_*)=n(xi_hat-xi_*), together with a yellow-brown contact dot. Add the yellow-brown text “score at xi_*”. Use the title “A single realization of ell_n(xi)” followed by “n=...”.

MIDDLE COLUMN — REPEATED SAMPLING:
Plot seven centered total log-likelihood realizations corresponding to representative standardized sample means sqrt(n)(X_bar-xi_*) near -1.35, -0.85, -0.35, 0, 0.35, 0.85, and 1.35. For deterministic reproduction, use random seed 762, simulate 4000 sample means from N(0,1/n), and choose the simulated value closest to each target. Draw all curves in translucent blue and put a blue dot at each maximum. Highlight three representative curves and draw thin yellow-brown tangents and yellow-brown contact dots at xi_*. Add a red dashed vertical line at xi_*=0. Overlay the expected log-likelihood shape, recentered to peak at zero, -(n/2)(xi-xi_*)^2, as a black dashed curve and label it “expected ell_n(xi)” without an arrow. Add the yellow-brown text “score at xi_*”. Use the title “Realizations of ell_n(xi) across samples” followed by “n=...”.

RIGHT COLUMN — SCORE DISTRIBUTION:
Plot the N(0,n) density of U_n(xi_*) using a solid blue curve. Use identical axes in the two rows: x from -25 to 25 and y from 0 to 0.16. Do not draw a vertical line at zero. In the upper-right region, add the two-line annotation
E{U_n(xi_*)}=0
Var{U_n(xi_*)}=n I_1(xi_*).
Label the x-axis “score U_n(xi_*)” and the y-axis “sampling density”. Use the title “Sampling distribution of U_n(xi_*)” followed by “n=...”.

Use serif STIX-style mathematical typography. Use #5A7FA5 for likelihood and density curves, #173F5F for MLE elements, #B23A48 for the truth line and truth tick, #C9862C for score tangents and score labels, and #30343B for expected curves and neutral annotations. Use subtle horizontal grid lines, remove the top and right spines, and keep tangent lines thin. Do not include shaded areas, arrows, panel labels such as (a)-(f), or a caption inside the plot.

Use a figure size of 10.6 by 6.25 inches. Export the result as vector PDF and SVG files and as a 300-dpi PNG with a white background and tight bounding box.