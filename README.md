# Paint4Net: visualisation toolbox for COBRA

Author(s):
Andrejs Kostromins, Biosystems Group, Department of Computer Systems, Latvia University of Agriculture,
Liela iela 2, LV-3001 Jelgava, Latvia.

Egils Stalidzans, Institute of Microbiology and Biotechnology, University of Latvia, Jelgavas iela 1, LV-1004,
Latvia.

Modified for use in modern versions of MatLab by Rui Afonso Tavares, Līva Lukaša & Reinis Muižnieks, 2026.
Reviewer(s):

Agris Pentjuss, Institute of Microbiology and Biotechnology, University of Latvia, Jelgavas iela 1, LV-1004,
Latvia.

Almut Heinken, Luxembourg Centre for Systems Biomedicine, Universiy of Luxembourg, 6 avenue du Swing,
Belvaux, L-4367, Luxembourg.

## IMPORTANT NOTE
Paint4Net uses Bioinformatics Toolbox to generate visualisation layout, however it is not supported in .mlx
causing an error during function execution. Thus the functions involving visualisation were run in regular
MATLAB command window and each visualisation layout was saved as a static figure and placed in the .mlx
tutorial, while the corresponding functions were run in .mlx with visualisation feature turned off (input argument
drawMap was set to 'false') to get outputs (without visualisation) in .mlx without crashing. Be aware of this issue
when you are running the functions in .mlx. All drawMap input arguments are set to 'true' in .mlx. Change it to
'false' to avoid an error.

## INTRODUCTION
A visual analysis of reconstructions and large stoichiometric models with elastic change of the visualization
scope and representation methods becomes increasingly important due to the rapidly growing size and number
of available reconstructions.
The Paint4Net is a COBRA Toolbox extension for automatic generation of a hypergraph layout of defined scope
with the steady state rates of reaction fluxes of stoichiometric models. Directionalities and fluxes of reactions are
constantly represented in the visualization while detailed information about reaction (ID, name and synonyms,
and formula) and metabolite (ID, name and synonyms, and charged formula) appears placing the cursor on
the item of interest. Additionally Paint4Net functionality can be used to: (1) get lists of involved metabolites
and dead end metabolites of the visualized part of the network, (2) exclude (filter) particular metabolites from
representation, (3) find isolated parts of a network and (4) find running cycles when all the substrates are cut
down. Layout pictures can be saved in various formats and easily distributed.


Two functions with their arguments are used in the Paint4Net to define the scope of visualization:
(1) [involvedMets, deadEnds] = draw by rxn(model, rxns, drawMap, direction, initialMet, excludeMets,
flux) – to define scope by a list of reactions and (2) [directionRxns, involvedMets, deadEnds] = drawby met(model, metAbbr, drawMap, radius, direction, excludeMets, flux) – to define the metabolite of interest to see linked reactions within radius of, for instance, 2 reactions. The function draw_by_rxn has input arguments: (1) model – stands for stoichiometric reconstruction or model with constraints, (2) rxns –
stands for a list of the reactions of interest for analysis, (3) drawMap (optional) – stands for request to generate
visualization ('true' or 'false', default is 'false'), (4) direction (optional) – stands for algorithm visualization mode
('struc', 'sub', 'prod' or 'both') in order to visualize structure (struc) of reconstructions without FBA data or
visualize substrates (sub), products (prod) or substrates and products (both) for models with flux constraints and
FBA data (default is 'struc'), (5) initialMet (optional) – stands for metabolite of interest to be used by function
draw by met (default is empty), (6) excludeMets (optional) – stands for a list of the excludable metabolites as
a filter and (7) flux (optional) – stands for vector of FBA data of reactions flux distribution (default is vector
of x characters if flux is not calculated). 

The last 5 arguments are optional and can be unset. The functiondraw_by_rxn has 2 outputs: (1) involvedMets – stands for a list of involved metabolites depending on the input arguments and (2) deadEnds – stands for a list of dead-end metabolites depending on the input arguments. The
function draw_by_met has 7 input arguments: (1) model – stands for stoichiometric reconstruction or model with
constraints, (2) metAbbr – stands for an input for metabolite of interest for analysis, (3) drawMap (optional) –
stands for request to generate visualization ('true' or 'false', default is 'false'), (4) radius – stands for distance
indicator between metabolite of interest and involved reactions (default is 1), (5) direction – stands for algorithm
visualization mode ('struc', 'sub', 'prod' or 'both') in order to visualize structure (struc) of reconstructions without
FBA data or visualize substrates (sub), products (prod) or substrates and products (both) for models with flux
constraints and FBA data (default is 'struc'), (6) excludeMets (optional) – stands for a list of the excludable
metabolites as a filter and (7) flux – stands for vector of FBA data of reactions flux distribution (default is vector
of x characters for no flux). The last 5 arguments were optional in previous releases, and could be unset but
are now required in the updated version. The function draw_by_met ha s 3 outputs: (1) directionRxns – stands
for a list of involved reactions depending on the input arguments, (2) involvedMets – stands for a list of involved
metabolites depending on the input arguments and (3) deadEnds – stands for alist of dead-end metabolites
depending on the input arguments.

 

​
Citation

Kostromins A., Stalidzans E. (2012) Paint4Net: COBRA Toolbox extension for visualization of stoichiometric models of metabolism. Biosystems, 109(2), pp. 233–239. https://doi.org/10.1016/j.biosystems.2012.03.002


​
Heirendt, L., Arreckx, S., Pfau, T., Mendoza, S.N., Richelle, A., Heinken, A., Haraldsdottir, H.S., Keating, S.M., Vlasov, V., Wachowiak, J., Magnusdottir, S., Ng, C.Y., Preciat, G., Zagare, A., Chan, S.H.J., Aurich, M.K., Clancy, C.M., Modamio, J., Sauls, J.T., Noronha, A., Bordbar, A., Cousins, B., Assal, D.C. El, Ghaderi, S., Ahookhosh, M., Guebila, M. Ben, Apaolaza, I., Kostromins, A., Le, H.M., Ma, D., Sun, Y., Valcarcel, L. V., Wang, L., Yurkovich, J.T., Vuong, P.T., Assal, L.P. El, Hinton, S., Bryant, W.A., Artacho, F.J.A., Planes, F.J., Stalidzans, E., Maass, A., Vempala, S., Hucka, M., Saunders, M.A., Maranas, C.D., Lewis, N.E., Sauter, T., Palsson, B.Ø., Thiele, I., Fleming, R.M. (2019) Creation and analysis of biochemical constraint-based models: the COBRA Toolbox v3.0. Nature Protocols, 14, pp. 639–702. https://doi.org/10.1038/s41596-018-0098-2

​

