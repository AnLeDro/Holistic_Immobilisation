---
repo: "https://github.com/"
prefix: "Immobilisior"
---

# Immobilisation
Description: Immobilization is a crucial technique in biotechnology where enzymes or cells are physically or chemically attached to a solid support material. This process enhances enzyme stability, enables reuse, and facilitates continuous bioprocessing operations.

## Root Objects

### Immobilisation_Spec
Description: Specification for enzyme immobilization process, including details about the enzyme and immobilization parameters.

- enzyme
  - Type: Enzyme
  - Description: Details of the enzyme to be immobilized, including source and characteristics
- immobilisation
  - Type: Immobilisation
- storage_conditions
  - Type: StorageConditions
- catalytic_performance
  - Type: CatalyticPerformance
- mKPIs_efficiency
  - Type: mKPIsEfficiency

## General information

### Enzyme
- purchase
  - Type: Purchase
  - Description: Information about commercially acquired enzymes
- produced
  - Type: Produced
  - Description: Details for in-house produced enzymes
- as_sequ
  - Type: string
- spec_activity_wt
  - Type: integer
  - Description: Specific activity in [U/mg] of the wildtype enzyme.
- reaction_spec_activity
  - Type: string
  - Desription: Substrate used for determination of specific activity. 

### Purchase
- supplier
  - Type: string
- cas_num
  - Type: string
- eg_num
  - Type: string
- host_org
  - Type: string
- purity
  - Type: integer
  - Description : in %
- spec_activity
  - Type: integer
  - Description: U/mg
- reaction_spec_activity
  - Type: string
  - Desription: Substrate used for determination of specific activity. 

### Produced

Description: Specifications for enzymes produced in-house through biotechnological processes
- modification
  - Type: Modification
  - Description: Details of any genetic or chemical modifications made to the enzyme
- usp
  - Type: USP
  - Description: Upstream processing parameters and conditions
- harvest
  - Type: Harvest
  - Description: Parameters and methods for cell harvesting and product recovery

### Modification

Description: Specifications for enzyme modifications to enhance functionality or facilitate purification
- spec_activity
  - Type: integer
  - Description: Specific activity of the modified enzyme in [U/mg]
- reaction_spec_activity
  - Type: string
  - Desription: Substrate used for determination of specific activity. 
- tag
  - Type: string
  - Description: Type of affinity tag added to the enzyme
- display
  - Type: string
  - Description: Information on the enzyme display used as immobilisation technique (surface display, inclusion body display, ...). 
- mutation
  - Type: string
  - Description: Any point mutations introduced into the enzyme sequence

### USP

Description: Parameters and specifications for upstream processing of enzyme production
- process_mode
  - Type: Processmode
  - Description: Mode of fermentation operation 
- USP_KPIs
  - Type: USPKPIs
  - Description: KPIs calculated for the USP section.

### USPKPIs
- scale
  - Type: integer
  - Description: Final volume of the fermentation broth.
- time_USP
  - Type: integer
  - Description: Time used for USP in [h].
- STY_USP
  - Type: integer
  - Description: Productivity (space-time-yield) of the process.
- Product_yield_per_substrate
  - Type: integer
  - Description: Product yield per used substrate.
- Product_yield_per_biomass
  - Type: integer
  - Description: Product yield per used biomass.
- Units_per_liter_of_fermentation_broth
  - Type: integer
  - Description: 
- Amount_of_enzyme_per_liter_of_fermentation_broth
  - Type: integer
  - Description: 
- Total_Units
  - Type: integer
  - Description:


### Harvest

Description: Methods and parameters for harvesting cells and recovering the enzyme product
- cells
  - Type: Cells
  - Description: Processing steps for intracellular enzymes
- supernatant
  - Type: Supernatant
  - Description: Processing steps for extracellular enzymes
- harvest_KPIs
  - Type: HarvestKPIs
  - Description


### Cells
- cell_lysis
  - Type: string
  - Description: Method used to break open cells
- centrifugation
  - Type: string
  - Description: Parameters for cell separation by centrifugation
- cells_or_extract_as_product
  - Type: CellsOrExtractAsProduct
- purification
  - Type: Purification[]
  - Description: Series of purification steps applied to the cell extract

### Supernatant
- centrifugation
  - Type: string
  - Description: Parameters for removing cell debris from culture medium
- purification
  - Type: Purification[]
  - Description: Series of purification steps applied to the supernatant

### Purification
- step_no
  - Type: integer
- pur_method
  - Type: PurMethod
- method_description
  - Type: string
 
### HarvestKPIs
- mg_enzyme_recovered
  - Type: integer
  - Description:
- U_enzyme_recovered
  - Type: integer
  - Description:    

### Immobilisation

- immobilisation_chemistry
  - Type: string
  - Description: This aspect denotes the specific chemical methods or techniques used to attach the enzymes onto the chosen base material. Different immobilisation chemistries involve various covalent or non-covalent bonding strategies, including adsorption, covalent bonding, specific binding via (affinity)tag, entrapment or crosslinking.
- carrier_binding
  - Type: CarrierBinding
  - Description: Carrier-binding is referred to all non-covalent and covalent immobilisation techniques, requiering a support material, base, cell or carrier.  
- entrapment
  - Type: Entrapment
  - Description: Entrapment immobilisation techniques include the encapsulation and entrapment od the enzyme in a matrix.  
- carrier_free
  - Type: CarrierFree
  - Description: Carrier-free immobilisation refers to the crosslinking of enzymes.
- immo_kpis
	- Type: ImmoKPIs

### CarrierBinding
- material
  - Type: string
  - Description: If a support material, base, or carrier was utilized, it is necessary to specify the material's name (e.g., gel, membrane, particle) along with the supplier and further product details. 
- method
  - Type: string
- surface_modification
  - Type: string

### Entrapment
- material
  - Type: string
- method
  - Type: string

### CarrierFree
- method
  - Type: string

### ImmoKPIs
- immobilisation_yield
	- Type: integer 
	- Description: The immobilisation yield Y_I is defined as the proportion of used enzyme (mgE) that is immobilised on the carrier material
- activity_yield
	- Type: integer
	- Description: The activity yield is defined as the enzyme units found on the carrier after immobilisation divided by the units of free enzyme used for the immobilisation. The activity yield can exceed 100% in the case of an activation of the enzyme upon immobilisation but accurate determination requires a method of activity measurement for the immobilised enzyme.
- specific_activity
	- Type: integer
	- Description: The specific activity of the immobilised enzyme A_(spec. immo) describes the Units per mg of immobilised enzyme.
- change_spec_activity
	- Type: integer 
	- Description: The Aspec. describes the change in specific activity of the free enzyme compared to the immobilised enzyme.
- Loading
	- Type: integer 
	- Description: The enzyme loading describes the enzyme units immobilised per mass of immobilisation carrier.

### StorageConditions
- temperature
   - Type: integer
- additices
   - Type: string
- storage_performance_t12
   - Type: integer
- spec_activity
   - Type: integer
- storage_KPIs
   - Type: StorageKPIs

### StorageKPIs
- mg_recovered
   - Type: integer
- U_recovered
   - Type: integer

### CatalyticPerformance
- catalysed_reaction
	- Type: string
- components
    - Type: Components
- reaction_conditions
	- Type: ReactionConditions
- catalytic_KPIs
    - Type: CatalyticKPIs

### Components 
- Substrate
    - Type: string
- Substrate_smiles
    - Type: string
- Product  
    - Type: string
- Product_smiles
    - Type: string
- Co_substrate
    - Type: string
- Cosubstrate_smiles
    - Type: string
- Cofactor 
    - Type: string
- Cofactor_recycling_system
    - Type: string

### ReactionConditions
% übernehmen aus Strenda
- well_mixed_solutions
  	- Type: string
- tubular_flow
    - Type: string

### CatalyticKPIs
- conversion
    - Type: integer
- turnover_number
    - Type: integer
- turnover_frequency
    - Type: integer
- space_time_yield
    - Type: integer
- Enzyme_bleeding
    - Type: string
- Carrier_recovery
    - Type: string

### mKPIsEfficiency
- Recovered_activity_efficiency
	- Type: integer 
- Space_time_activity
	- Type: integer
- Total_volumetric_turnovers
	- Type: integer
- Total_process_productivity
	- Type: integer

 
## Enumerations

### Processmode
```python
BATCH = Batch
FEDBATCH = Fedbatch
CONTI = Continous
OTHER = Other
```

### PurMethod
```python
PRECITPITATION = Precipitation
CHROMATOGRAPHY = Chromatography
FILTRATION = Filtration
OTHER = Other
```

### CellsOrExtractAsProduct
```python
CELLS = Cells
EXTRACT = Extract
```
