# Prediction_of_Landscapes

# ABSTRACT
Landscapes are meaningful ecological units that strongly depend on the environmental conditions.
Such dependencies between landscapes and the environment have been noted since the beginning
of Earth sciences and cast into conceptual models describing the interdependencies of climate,
geology, vegetation and geomorphology. Here, we ask whether landscapes, as seen from space,
can be statistically predicted from pertinent environmental conditions. To this end we adapted a
deep learning generative model in order to establish the relationship between the environmental
conditions and the view of landscapes from the Sentinel-2 satellite. We trained a conditional
generative adversarial network to generate multispectral imagery given a set of climatic, terrain and
anthropogenic predictors. The generated imagery of the landscapes share many characteristics with
the real one. Results based on landscape patch metrics, indicative of landscape composition and
structure, show that the proposed generative model creates landscapes that are more similar to the
targets than the baseline models while overall reflectance and vegetation cover are predicted better.
We demonstrate that for many purposes the generated landscapes behave as real with immediate
application for global change studies. We envision the application of machine learning as a tool
to forecast the effects of climate change on the spatial features of landscapes, while we assess its
limitations and breaking points.
Accepted as a conference paper at GCPR2019
# 1 Introduction
The Earth’s land surface can be considered a mosaic of landscapes [1]. Landscapes are the material-physical entities
that comprise the structures of nature [2]: ecological meaningful units that have a characteristic ordering of elements
[3]. Landscapes result from the long-term interaction of abiotic, biotic and anthropogenic processes. The relation
between landscapes and the climatic, geological, and anthropogenic factors is, however, rather conceptual. The totality
of interactions and processes that determine the landscapes are impossible to simulate numerically as of today. This fact
holds true to such extent that, to the best of our knowledge, landscape imagery prediction is yet to be attempted. We aim
to analyze whether the relation between forming factors and landscapes can be mapped with a statistical method. Our
goal is to reconstruct the 2D aerial view (multispectral) of the landscapes from a set of 2D environmental conditions.
Furthermore, we assess the use of predicting landscapes as a tool for climate change and landscape change studies.
The study of Earth at the landscape scale gained momentum in the last decades benefiting from the use of geographic
information systems and the high availability of remotely sensed imagery [4, 5, 6, 7, 8]. Remotely sensed images are a
measure of the radiation reflected by the surface. The observed reflections at certain wavelength are information rich
snapshots that can be used to diagnose features such as land-cover type, ecosystem spatial structure, vegetation health,
water availability or human impact [9, 10, 11]. Predicting the aerial image comes close to predicting the landscapes and
their spatial arrangement. From the satellite image, one could derive many high level aspects of the landscapes and
ecosystems with existing earth observation tools.
Landscapes are formed by a wide range of components and processes. Factors that determine a landscape can be
categorized into largely independent ones (e.g. climate or geology) and dependent ones (e.g. soil or vegetation). A
change on the independent factor leads to a change of the dependent ones, for example, changes on abiotic factors
generally lead to changes in biotic components (such as shifting position or composition). Previous work to classify the
landscapes has determined and ranked the forming factors by importance [12, 13, 3]
L = f(C; G;H; S; V; F;U; S): (1)
Where L is the Landscape, C is climate, G the geology and geomorphology, H the hydrology, S the soil, V the
vegetation, F the fauna, U the land use and S the landscape structure. Developing over the work of [3] we can further
reduce the conceptual relationship into the essential independent forming factors
L = f(Clim; Geo; AI): (2)
Where Clim is the broadened climate, Geo is the lithology and topography and AI are the anthropogenic interventions.
As the dependent factors (e.g. soil or vegetation) can be thought of as a function of the independent ones (climate and
geology) direct knowledge is not strictly necessary. In addition we broad the definition of climate to encompass all of
the meteorological hydrology.
Mechanistic or statistical approaches are scarce, or only address certain aspects (e.g. geomorphological models).
Advances in deep learning allow for unsupervised content-based data driven modeling, i.e, neural networks capable of
learning the relationship between the spatial features present in the input and output from available data [14]. Ideally,
these networks can accommodate the non-linearities that best approximate the functional relation between environmental
factors and landscapes generating realistic spatial representations of the landscapes. We aim to demonstrate that it is
possible to predict landscapes -as seen from space- that behave as real for hypothetical environmental conditions. We
attempt to map the climatic, topographic and anthropogenic factors onto sentinel-2 visible and near-IR bands using
a conditional generative adversarial network (cGAN) [15]. We will assess its limitations and usability as a tool for
climate change studies. One of the main applications envisioned for the proposed approach is forecasting landscape
change under future climate projections.

