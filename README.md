# Z0 Precision measurement

We analyze data from large electron positron collider (LEP) at CERN in order to precisely determine properties of the Z0 boson. Additionally we test the Standard Model, determine the weak mixing angle or Weinberg angle and the number of light neutrino generations.

# Installing with conda

1. Install [anaconda](https://docs.anaconda.com/anaconda/install/) (miniconda probably works too?).
2. `conda env create` reads the `environment.yml` file in this
    repository, creates a new env and installs all necessary packages
    into it.
3. Activate the new env: `conda activate z0-env`
4. Start `jupyter-lab` (or `jupyter-notebook` if you prefer) in the
    environment. This will usually open your browser automatically. If
    not the link is printed to the console too.

# Content and usage

We use jupyter notebooks to write our code and analyze the data. These can be run completly from top to bottom. After execution they can be read like a report of our analysis. More detailed descriptions of our procedure and reasons for our specific choices can be found in the report (provided at a later date).

1. The jupyter notebook `z0_experiment.ipynb` contains the original instructions and gives hints how to solve certrain aspects of the calculations.
2. In the notebook `z0_Grope_analysis.ipynb` we analyze real detector events, that are presorted into their corresponding decay channels. This allows to define first guesses on the cuts that are used to identify the decay channels from unsorted data.
3. The notebook `z0_statistical_analysis.ipynb` contains the main parts of the analysis. Here the following steps are performed:
    - Analysis of sorted Monte Carlo simulated data near the resonance energy in order to:
      - refine cuts. Here we implemeted a tool that allows to visualize specific channels and cuts. This allows to easily optimize the efficiency matrix (see below) by iteratively moving the cuts. The usage is described in the notebook.
      - calculate efficiency matrix of the channel identification
      - separate s-channel from t- and s-t interference for electron channel
    - Analysis of real events at different collider energies:
      - calculate number of events in each channel and energy
      - determine total cross sections for all channels as function of energy
      - perform a fit with theoretically expected Breit-Wigner function
      - Measure Z0 mass, decay width, partial decay widths and number of light neutrino families
      - confirm lepton universality
      - calculate forward-backward-asymmetry and from this the Weinberg angle
    - In all steps uncertainties are propageted carefully.
4. The folders `opal_data` and `Grope_data` contain all data files used in notebooks `z0_statistical_analysis.ipynb` and `z0_Grope_analysis.ipynb`, respectively.
&nbsp;

