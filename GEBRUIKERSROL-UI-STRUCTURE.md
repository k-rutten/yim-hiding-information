# Gebruikersrol (User Role) - UI Structure Documentation

## Overview
This document outlines the complete editable sections and UI components for the Gebruikersrol (User Role) management form in the YIM system.

---

## Layout Architecture

### Page Structure
- **Left Sidebar**: Vertical navigation with 6 numbered tabs
- - **Main Content Area**: Form sections with tab-based organization
  - - **Footer Actions**: Back and Save buttons
   
    - ### Color Scheme
    - - **Primary Actions**: Teal/Green (#5EBBA4 or similar)
      - - **Headers**: Dark Blue (#2C4A5C or similar)
        - - **Backgrounds**: Light Gray (#F5F5F5 or similar)
          - - **Text**: Dark Gray/Black (#333 or similar)
           
            - ---

            ## Tab 1: INFORMATIE (Information)

            ### Section Description
            Basic information about the user role.

            ### Fields

            | Field Name | Field Label | Component Type | Required | Notes |
            |------------|-------------|-----------------|----------|-------|
            | `naam` | Naam | Text Input | Yes | Role name |
            | `omschrijving` | Omschrijving | Text Input | No | Role description |

            #### Field Specifications

            **Naam (Name)**
            - Type: `<input type="text">`
            - - Placeholder: Empty
              - - Validation: Required
                - - Max Length: Not specified
                 
                  - **Omschrijving (Description)**
                  - - Type: `<input type="text">`
                    - - Placeholder: Empty
                      - - Validation: Optional
                        - - Max Length: Not specified
                         
                          - ---

                          ## Tab 2: PROCESRECHTEN (Process Rights)

                          ### Section Description
                          Define which processes, tasks, and levels this role can access.

                          ### Fields

                          #### 1. Processen (Processes)

                          | Property | Value |
                          |----------|-------|
                          | Component | Dual Listbox |
                          | Label | Processen |
                          | Available Column | Beschikbaar |
                          | Selected Column | Geselecteerd |

                          **Available Options:**
                          - Gebruiker
                         
                          - **Selected Options:**
                          - - Bedrijf
                            - - Contractor
                              - - Bezoeker
                                - - Medewerker
                                 
                                  - ---

                                  #### 2. Contractor types

                                  | Property | Value |
                                  |----------|-------|
                                  | Component | Dual Listbox |
                                  | Label | Contractor types |
                                  | Available Column | Beschikbaar |
                                  | Selected Column | Geselecteerd |

                                  **Available Options:**
                                  - Medewerker JINC
                                  - - Contractor - alles aan
                                   
                                    - **Selected Options:**
                                    - - Contractor
                                     
                                      - ---

                                      #### 3. Taken (Tasks)

                                      | Property | Value |
                                      |----------|-------|
                                      | Component | Dual Listbox |
                                      | Label | Taken |
                                      | Available Column | Beschikbaar |
                                      | Selected Column | Geselecteerd |

                                      **Available Options (17 total):**
                                      - Aanmelden
                                      - - Autorisaties bewerken
                                        - - Deactivatie beoordelen
                                          - - Dossier bekijken
                                            - - Dossier beoordelen
                                              - - Dossier bewerken
                                                - - Dossier registreren
                                                  - - Foto upload
                                                    - - Handmatig het examen afronden
                                                      - - Heractivatie beoordelen
                                                        - - Identificatie aanvragen
                                                          - - Identificatie beoordelen
                                                            - - Identificatie intrekken
                                                              - - Inhuur- of Contractperiode beëindigen
                                                                - - Stuur E-learning uitnodiging
                                                                  - - Uploaden
                                                                    - - Voeg examenpoging toe
                                                                     
                                                                      - **Selected Options:**
                                                                      - - Autorisaties beoordelen
                                                                       
                                                                        - ---

                                                                        #### 4. Niveau (Level)

                                                                        | Property | Value |
                                                                        |----------|-------|
                                                                        | Component | Dropdown Combobox with expand button |
                                                                        | Label | Niveau |
                                                                        | Type | Searchable select |

                                                                        ---

                                                                        #### 5. Dossierniveau (File Level)

                                                                        | Property | Value |
                                                                        |----------|-------|
                                                                        | Component | Dual Listbox |
                                                                        | Label | Dossierniveau |
                                                                        | Available Column | Beschikbaar |
                                                                        | Selected Column | Geselecteerd |

                                                                        **Available Options:**
                                                                        - Aanmeldingen
                                                                        - - Autorisaties
                                                                          - - Certificates
                                                                            - - Dossier informatie
                                                                              - - Evenementen
                                                                                - - Gebruikers bedrijf
                                                                                  - - Geschiedenis
                                                                                    - - Identificaties
                                                                                      - - Personen bedrijf
                                                                                       
                                                                                        - ---

                                                                                        #### 6. Bestand toegangen (File Access)

                                                                                        | Property | Value |
                                                                                        |----------|-------|
                                                                                        | Component | Dual Listbox |
                                                                                        | Label | Bestand toegangen |
                                                                                        | Available Column | Beschikbaar |
                                                                                        | Selected Column | Geselecteerd |

                                                                                        **Available Options:**
                                                                                        - Certificaten
                                                                                        - - Persoonlijk
                                                                                         
                                                                                          - ---

                                                                                          #### 7. Locaties (Locations)

                                                                                          | Property | Value |
                                                                                          |----------|-------|
                                                                                          | Component | Dual Listbox |
                                                                                          | Label | Locaties |
                                                                                          | Available Column | Beschikbaar |
                                                                                          | Selected Column | Geselecteerd |

                                                                                          **Available Options (15 total):**
                                                                                          - ABC
                                                                                          - - Botlek Rotterdam
                                                                                            - - BP Raffinaderij Poort 1
                                                                                              - - DEF
                                                                                                - - Den Haag - The Zone - Bazalt Group
                                                                                                  - - Den Haag - The Zone - Coupry Advocaten
                                                                                                    - - Den Haag - The Zone - JINC
                                                                                                      - - Den Haag - The Zone - NIBC
                                                                                                        - - Emmen
                                                                                                          - - GHI
                                                                                                            - - Hoogeveen
                                                                                                              - - JKL
                                                                                                                - - Oss
                                                                                                                  - - Stadskanaal
                                                                                                                    - - Winkel
                                                                                                                     
                                                                                                                      - **Selected Options:**
                                                                                                                      - - Barendrecht
                                                                                                                        - - Diemen
                                                                                                                          - - Rotterdam
                                                                                                                            - - Schiphol
                                                                                                                             
                                                                                                                              - ---
                                                                                                                              
                                                                                                                              #### 8. Dagtijdschema's (Time Schedules)
                                                                                                                              
                                                                                                                              | Property | Value |
                                                                                                                              |----------|-------|
                                                                                                                              | Component | Dual Listbox |
                                                                                                                              | Label | Dagtijdschema's |
                                                                                                                              | Available Column | Beschikbaar |
                                                                                                                              | Selected Column | Geselecteerd |
                                                                                                                              
                                                                                                                              **Available Options:**
                                                                                                                              - Overwerk
                                                                                                                             
                                                                                                                              - **Selected Options:**
                                                                                                                              - - 24/7
                                                                                                                                - - Kantooruren
                                                                                                                                 
                                                                                                                                  - ---
                                                                                                                                  
                                                                                                                                  #### 9. Zones
                                                                                                                                  
                                                                                                                                  | Property | Value |
                                                                                                                                  |----------|-------|
                                                                                                                                  | Component | Dual Listbox |
                                                                                                                                  | Label | Zones |
                                                                                                                                  | Available Column | Beschikbaar |
                                                                                                                                  | Selected Column | Geselecteerd |
                                                                                                                                  
                                                                                                                                  **Available Options (8 total):**
                                                                                                                                  - Bezoeker
                                                                                                                                  - - The Zone - NIBC - Compliance & Legal
                                                                                                                                    - - The Zone - NIBC - Facility & Services
                                                                                                                                      - - The Zone - NIBC - Human Resources
                                                                                                                                        - - The Zone - NIBC - IT & Digital
                                                                                                                                          - - The Zone - NIBC - Office Services
                                                                                                                                            - - The Zone - NIBC - Security & Safety
                                                                                                                                              - - VIP
                                                                                                                                               
                                                                                                                                                - **Selected Options (8 total):**
                                                                                                                                                - - Facilitair
                                                                                                                                                  - - Schoonmaak
                                                                                                                                                    - - The Zone - NIBC - IT
                                                                                                                                                      - - Zone A
                                                                                                                                                        - - Zone Noord
                                                                                                                                                          - - Zone Oost
                                                                                                                                                            - - Zone West
                                                                                                                                                              - - Zone Zuid
                                                                                                                                                               
                                                                                                                                                                - ---
                                                                                                                                                                
                                                                                                                                                                ## Tab 3: OVERZICHTEN (Overviews)
                                                                                                                                                                
                                                                                                                                                                ### Section Description
                                                                                                                                                                Configure which overview/reports this role can access.
                                                                                                                                                                
                                                                                                                                                                ### Fields
                                                                                                                                                                
                                                                                                                                                                #### Overzichten (Overviews)
                                                                                                                                                                
                                                                                                                                                                | Property | Value |
                                                                                                                                                                |----------|-------|
                                                                                                                                                                | Component | Dual Listbox |
                                                                                                                                                                | Label | Overzichten |
                                                                                                                                                                | Available Column | Beschikbaar |
                                                                                                                                                                | Selected Column | Geselecteerd |
                                                                                                                                                                
                                                                                                                                                                **Available Options (13 total):**
                                                                                                                                                                - Aanmeldingen
                                                                                                                                                                - - Aanwezigheidsregistratie
                                                                                                                                                                  - - Accreditaties
                                                                                                                                                                    - - Bedrijven
                                                                                                                                                                      - - Bezoekers
                                                                                                                                                                        - - Contractors
                                                                                                                                                                          - - Identificatie aanvragen
                                                                                                                                                                            - - Identificatie accreditaties
                                                                                                                                                                              - - Identificatie orders
                                                                                                                                                                                - - Identificatie print
                                                                                                                                                                                  - - Identificaties meervoudig
                                                                                                                                                                                    - - Medewerkers
                                                                                                                                                                                      - - Verwachte bezoekers
                                                                                                                                                                                       
                                                                                                                                                                                        - ---
                                                                                                                                                                                        
                                                                                                                                                                                        ## Tab 4: RAPPORTEN (Reports)
                                                                                                                                                                                        
                                                                                                                                                                                        ### Section Description
                                                                                                                                                                                        Configure which reports this role can access.
                                                                                                                                                                                        
                                                                                                                                                                                        ### Fields
                                                                                                                                                                                        
                                                                                                                                                                                        #### Rapporten (Reports)
                                                                                                                                                                                        
                                                                                                                                                                                        | Property | Value |
                                                                                                                                                                                        |----------|-------|
                                                                                                                                                                                        | Component | Dual Listbox |
                                                                                                                                                                                        | Label | Rapporten |
                                                                                                                                                                                        | Available Column | Beschikbaar |
                                                                                                                                                                                        | Selected Column | Geselecteerd |
                                                                                                                                                                                        
                                                                                                                                                                                        **Available Options:**
                                                                                                                                                                                        - temp-report
                                                                                                                                                                                       
                                                                                                                                                                                        - ---
                                                                                                                                                                                        
                                                                                                                                                                                        #### Verouderde rapporten (Legacy Reports)
                                                                                                                                                                                        
                                                                                                                                                                                        | Property | Value |
                                                                                                                                                                                        |----------|-------|
                                                                                                                                                                                        | Component | Dual Listbox |
                                                                                                                                                                                        | Label | Verouderde rapporten |
                                                                                                                                                                                        | Available Column | Beschikbaar |
                                                                                                                                                                                        | Selected Column | Geselecteerd |
                                                                                                                                                                                        
                                                                                                                                                                                        **Available Options (4 total):**
                                                                                                                                                                                        - Aanwezigheid
                                                                                                                                                                                        - - Calamiteiten
                                                                                                                                                                                          - - Tijdregistratie
                                                                                                                                                                                            - - Rapportage zones
                                                                                                                                                                                             
                                                                                                                                                                                              - ---
                                                                                                                                                                                              
                                                                                                                                                                                              ## Tab 5: BEHEERRECHTEN (Management Rights)
                                                                                                                                                                                              
                                                                                                                                                                                              ### Section Description
                                                                                                                                                                                              Configure administrative/management permissions for this role.
                                                                                                                                                                                              
                                                                                                                                                                                              ### Fields
                                                                                                                                                                                              
                                                                                                                                                                                              #### Beheerrechten (Management Rights)
                                                                                                                                                                                              
                                                                                                                                                                                              | Property | Value |
                                                                                                                                                                                              |----------|-------|
                                                                                                                                                                                              | Component | Dual Listbox |
                                                                                                                                                                                              | Label | Beheerrechten |
                                                                                                                                                                                              | Available Column | Beschikbaar |
                                                                                                                                                                                              | Selected Column | Geselecteerd |
                                                                                                                                                                                              
                                                                                                                                                                                              **Available Options (45 total):**
                                                                                                                                                                                              - Admin toegang certificatie
                                                                                                                                                                                              - - Administrator
                                                                                                                                                                                                - - Afdelingen
                                                                                                                                                                                                  - - Afwijsredenen
                                                                                                                                                                                                    - - Autorisatie rollen
                                                                                                                                                                                                      - - Autorisaties
                                                                                                                                                                                                        - - Bedrijven deactiveren
                                                                                                                                                                                                          - - Bedrijven heractiveren
                                                                                                                                                                                                            - - Bedrijvenstructuur
                                                                                                                                                                                                              - - Bezoek locaties
                                                                                                                                                                                                                - - Bezoekredenen
                                                                                                                                                                                                                  - - Contractor types
                                                                                                                                                                                                                    - - Dagtijdschema's
                                                                                                                                                                                                                      - - Delegeren
                                                                                                                                                                                                                        - - Elearning verbindingen
                                                                                                                                                                                                                          - - Evenement Autorisaties
                                                                                                                                                                                                                            - - Evenement typen
                                                                                                                                                                                                                              - - Evenementen
                                                                                                                                                                                                                                - - Foto controle
                                                                                                                                                                                                                                  - - Foto instructies
                                                                                                                                                                                                                                    - - Functies
                                                                                                                                                                                                                                      - - Gebruikers
                                                                                                                                                                                                                                        - - Gebruikersrollen
                                                                                                                                                                                                                                          - - Gedeactiveerde bedrijven bekijken
                                                                                                                                                                                                                                            - - Identificatie types
                                                                                                                                                                                                                                              - - Identificatie vervangredenen
                                                                                                                                                                                                                                                - - Identificatieaanvraag configuratie
                                                                                                                                                                                                                                                  - - Identificatieaanvraag locaties
                                                                                                                                                                                                                                                    - - Inhuur- of Contractperiode limiet
                                                                                                                                                                                                                                                      - - Koppelen/Ontkoppelen identifiers
                                                                                                                                                                                                                                                        - - Locaties
                                                                                                                                                                                                                                                          - - Nummerreeksen
                                                                                                                                                                                                                                                            - - Onboarding regels
                                                                                                                                                                                                                                                              - - Ongeluk frequentie
                                                                                                                                                                                                                                                                - - Processen
                                                                                                                                                                                                                                                                  - - Rapportages
                                                                                                                                                                                                                                                                    - - Tenant bedrijf
                                                                                                                                                                                                                                                                      - - Toegangsregel set verlengen
                                                                                                                                                                                                                                                                        - - Toegangsregel sets
                                                                                                                                                                                                                                                                          - - Toegangsregelautorisaties
                                                                                                                                                                                                                                                                            - - Vips zoeken
                                                                                                                                                                                                                                                                              - - Zones
                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                - ---
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ## Tab 6: DELEGATIE (Delegation)
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ### Section Description
                                                                                                                                                                                                                                                                                Configure role delegation settings.
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ### Fields
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                #### Rol kan worden gedelegeerd (Role Can Be Delegated)
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                | Property | Value |
                                                                                                                                                                                                                                                                                |----------|-------|
                                                                                                                                                                                                                                                                                | Component | Radio Button Group |
                                                                                                                                                                                                                                                                                | Label | Rol kan worden gedelegeerd |
                                                                                                                                                                                                                                                                                | Options | Ja (Yes), Nee (No) |
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ---
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ## Tab 6: BEDRIJVEN (Companies)
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ### Section Description
                                                                                                                                                                                                                                                                                Configure company/organization accreditation settings.
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ### Fields
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                #### Accrediteer alle bedrijven (Accredit All Companies)
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                | Property | Value |
                                                                                                                                                                                                                                                                                |----------|-------|
                                                                                                                                                                                                                                                                                | Component | Radio Button Group |
                                                                                                                                                                                                                                                                                | Label | Accrediteer alle bedrijven |
                                                                                                                                                                                                                                                                                | Options | Ja (Yes), Nee (No) |
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ---
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ## ACTION BUTTONS
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                | Button | Label | Type | Position | Action |
                                                                                                                                                                                                                                                                                |--------|-------|------|----------|--------|
                                                                                                                                                                                                                                                                                | Back | Terug | Secondary Button | Bottom Left | Navigate back |
                                                                                                                                                                                                                                                                                | Save | Opslaan | Primary Button | Bottom Right | Save all changes |
                                                                                                                                                                                                                                                                                | Stop Claude | Stop Claude | Special Button | Bottom Right | Stop automation |
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ---
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ## UI COMPONENT PATTERNS
                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                ### Dual Listbox Pattern
                                                                                                                                                                                                                                                                                - **Layout**: Two-column layout side-by-side
                                                                                                                                                                                                                                                                                - - **Left Column**: "Beschikbaar" (Available) - lists all available items
                                                                                                                                                                                                                                                                                  - - **Right Column**: "Geselecteerd" (Selected) - lists selected items
                                                                                                                                                                                                                                                                                    - - **Interaction**: Drag and drop or arrow buttons between lists
                                                                                                                                                                                                                                                                                      - - **Scrollable**: Both columns have independent scrollbars
                                                                                                                                                                                                                                                                                        - - **Search**: Search field above available options
                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                          - ### Text Input Pattern
                                                                                                                                                                                                                                                                                          - - **Style**: Light gray background (#F5F5F5)
                                                                                                                                                                                                                                                                                            - - **Border**: Subtle gray border
                                                                                                                                                                                                                                                                                              - - **Padding**: Standard form padding
                                                                                                                                                                                                                                                                                                - - **Focus State**: Teal/blue focus ring
                                                                                                                                                                                                                                                                                                  - - **Placeholder**: Descriptive placeholder text
                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                    - ### Dropdown/Combobox Pattern
                                                                                                                                                                                                                                                                                                    - - **Style**: Searchable select input
                                                                                                                                                                                                                                                                                                      - - **Arrow Icon**: Dropdown indicator on right
                                                                                                                                                                                                                                                                                                        - - **Expand Button**: Optional expand button for complex selections
                                                                                                                                                                                                                                                                                                          - - **Options**: Scrollable list of options
                                                                                                                                                                                                                                                                                                            - - **Search**: Type to filter options
                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                              - ### Radio Button Pattern
                                                                                                                                                                                                                                                                                                              - - **Layout**: Horizontal or vertical buttons
                                                                                                                                                                                                                                                                                                                - - **Style**: Two button options (Ja/Nee)
                                                                                                                                                                                                                                                                                                                  - - **Active State**: Highlighted/selected button
                                                                                                                                                                                                                                                                                                                    - - **Inactive State**: Outlined/unselected button
                                                                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                      - ### Section Headers
                                                                                                                                                                                                                                                                                                                      - - **Typography**: Large, bold, dark blue
                                                                                                                                                                                                                                                                                                                        - - **Spacing**: Clear vertical separation
                                                                                                                                                                                                                                                                                                                          - - **Border**: Underline or border accent
                                                                                                                                                                                                                                                                                                                            - - **Hierarchy**: H2 or H3 level
                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                              - ---
                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                              ## LAYOUT SPECIFICATIONS
                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                              ### Sidebar Navigation
                                                                                                                                                                                                                                                                                                                              - **Width**: ~250px
                                                                                                                                                                                                                                                                                                                              - - **Position**: Fixed, left side
                                                                                                                                                                                                                                                                                                                                - - **Tabs**: 6 numbered tabs
                                                                                                                                                                                                                                                                                                                                  - - **Active Indicator**: Orange/brown vertical line
                                                                                                                                                                                                                                                                                                                                    - - **Font**: Regular weight, light gray text
                                                                                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                      - ### Main Content Area
                                                                                                                                                                                                                                                                                                                                      - - **Max Width**: ~1100px
                                                                                                                                                                                                                                                                                                                                        - - **Padding**: Standard form padding
                                                                                                                                                                                                                                                                                                                                          - - **Background**: Light gray
                                                                                                                                                                                                                                                                                                                                            - - **Column Layout**: Single column for all fields
                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                              - ### Spacing
                                                                                                                                                                                                                                                                                                                                              - - **Field Spacing**: 20-30px between fields
                                                                                                                                                                                                                                                                                                                                                - - **Section Spacing**: 40-50px between major sections
                                                                                                                                                                                                                                                                                                                                                  - - **Button Spacing**: 15px between buttons
                                                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                                    - ---
                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                    ## VALIDATION RULES
                                                                                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                                    ### Naam (Name)
                                                                                                                                                                                                                                                                                                                                                    - Required field
                                                                                                                                                                                                                                                                                                                                                    - - Cannot be empty
                                                                                                                                                                                                                                                                                                                                                      - - Minimum length: Not specified
                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                        - ### All Dual Listboxes
                                                                                                                                                                                                                                                                                                                                                        - - Optional (no minimum selections required)
                                                                                                                                                                                                                                                                                                                                                          - - Multiple selections allowed
                                                                                                                                                                                                                                                                                                                                                            - - Items must exist in available options
                                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                              - ### Radio Buttons
                                                                                                                                                                                                                                                                                                                                                              - - One option must always be selected
                                                                                                                                                                                                                                                                                                                                                                - - Cannot be unselected
                                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                                  - ---
                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                  ## RESPONSIVE CONSIDERATIONS
                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                  - Sidebar may collapse on smaller screens
                                                                                                                                                                                                                                                                                                                                                                  - - Dual listboxes may stack vertically on mobile
                                                                                                                                                                                                                                                                                                                                                                    - - Form may need horizontal scrolling on small devices
                                                                                                                                                                                                                                                                                                                                                                      - - Button layout may change to stacked on mobile
                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                        - ---
                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                        ## ACCESSIBILITY NOTES
                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                        - All form fields have associated labels
                                                                                                                                                                                                                                                                                                                                                                        - - Tab navigation available
                                                                                                                                                                                                                                                                                                                                                                          - - Keyboard shortcuts supported
                                                                                                                                                                                                                                                                                                                                                                            - - Color contrast meets WCAG standards
                                                                                                                                                                                                                                                                                                                                                                              - - ARIA labels recommended for screen readers
                                                                                                                                                                                                                                                                                                                                                                                - - Form validation messages should be announced
                                                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                                                  - ---
                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                  ## INTEGRATION NOTES
                                                                                                                                                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                                                                  - Form submits to role management backend
                                                                                                                                                                                                                                                                                                                                                                                  - - Loads existing role data on edit
                                                                                                                                                                                                                                                                                                                                                                                    - - Performs validation before submission
                                                                                                                                                                                                                                                                                                                                                                                      - - Shows success/error messages on completion
                                                                                                                                                                                                                                                                                                                                                                                        - - May trigger related updates to other roles/permissions
                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                          - 
