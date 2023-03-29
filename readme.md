## CCLF File Specs as CSVs

#### CCLF files don't naturally have headers or delimiters, but I need these files as flat files. 

#### CMS provides a PDF document with tables that contain this information. This repository has those tables all cleaned up and as seperate CSVs for each CCLF filetype. These CSVs specifying the CCLF file Specifications can then be used to convert CCLF files into CSVs.

###

### important notes
    - Any occurence of the following columns in any of the tables has been renamed accordingly. 
            {'Element Name' : 'field_label',
            'Data Description' : 'field_name',
            'Beneficiary Field Name' : 'field_name',
            'Beneficiary Field Label' : 'field_label',
            'Claim Field Label' : 'field_label',
            'Claim Field Name' : 'field_name'}

    -A column "new_end_position" has been added. This field uses 0-based indexing as opposed to the 1-based indexing that CMS uses in thir "End Position" field. This field is calculated as follows: 
        df['Element #'] + df['End Position'] - 1
    
    This field specifies the positions at which the delimiter for a parsed CCLF file should be added. 