---
repo: "https://github.com/"
prefix: "Immobilisior"
---

# Immobilisationx
Description: Immobilization is a crucial technique in biotechnology where enzymes or cells are physically or chemically attached to a solid support material. This process enhances enzyme stability, enables reuse, and facilitates continuous bioprocessing operations.

## Root Objects

### Immobilisation_Spec
Description: Specification for enzyme immobilization process, including details about the enzyme and immobilization parameters.

- enzyme
  - Type:Enzyme
  - Description: Details of the enzyme to be immobilized, including source and characteristics
- immobilisation
  - Type: Immobilisation


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
  - Description: Specific activity of the modified enzyme in U/mg
- tag
  - Type: string
  - Description: Type of affinity tag added to the enzyme
- display
  - Type: string
  - Description: Location and details of the affinity tag
- mutation
  - Type: string
  - Description: Any point mutations introduced into the enzyme sequence

### USP

Description: Parameters and specifications for upstream processing of enzyme production
- process_mode
  - Type: Processmode
  - Description: Mode of fermentation operation
- scale
  - Type: integer
- kpi_i
  - Type: integer
  - Description: Key performance indicator for biomass yield
- kpi_ii
  - Type: integer
  - Description: Key performance indicator for substrate utilization
- kpi_iii
  - Type: integer
  - Description: Key performance indicator for product formation

### Harvest

Description: Methods and parameters for harvesting cells and recovering the enzyme product
- cells
  - Type: Cells
  - Description: Processing steps for intracellular enzymes
- supernatant
  - Type: Supernatant
  - Description: Processing steps for extracellular enzymes


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

### Immobilisation

- immobilisation_chemistry
  - Type: string
- carrier_binding
  - Type: CarrierBinding
- entrapment
  - Type: Entrapment
- carrier_free
  - Type: CarrierFree
- immo_kpis
	- Type: ImmoKPIs

### CarrierBinding
- material
  - Type: string
- preparation
  - Type: string
- surface_modification
  - Type: string

### Entrapment
- material
  - Type: string

### CarrierFree
- technique
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
