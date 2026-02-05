# YIM Data Privacy - Settings Configuration Project

## Project Overview

**Platform:** YIM SaaS (Visitor & Contractor Management System)  
**Prototype URL:** https://yim-hiding-information-7mgy.vercel.app/  
**Objective:** Add a settings interface to configure role-based data access permissions

---

## Current Status: Task 1 - Define Settings Concept ✅

### Context

The YIM platform manages sensitive personal data with role-based access control. Currently, the prototype demonstrates data masking with hardcoded role permissions. We need to add a settings panel where administrators can configure these permissions.

### Data Categories (4 categories)

1. **Persoonsgegevens** (Personal Data)
   - firstName, lastName
   - email ⚠️ SENSITIVE
   - phone ⚠️ SENSITIVE
   - dateOfBirth ⚠️ SENSITIVE
   - bsn ⚠️ SENSITIVE (Dutch Social Security)
   - nationality
   - address ⚠️ SENSITIVE

2. **Arbeidsgegevens** (Employment Data)
   - company, kvkNumber, employeeNumber
   - function, department, contractType, startDate

3. **Compliance Data**
   - VCA (status, expiryDate, number)
   - VOG (status, expiryDate, number)
   - Safety training, COVID certification

4. **Toegangsrechten** (Access Rights)
   - sites, zones, cardNumber
   - validUntil, lastAccess

---

## Permission Levels (5 levels)

1. **Volledig** (Full) - Complete access to all data
2. **Gedeeltelijk** (Partial) - Partially masked (e.g., ja••••@domain.nl)
3. **Samenvatting** (Summary) - Shows "✓ Beschikbaar"
4. **Minimaal** (Minimal) - Shows ••••••••
5. **Verborgen** (Hidden) - Not visible at all

---

## Existing Roles (15+ roles identified)

From YIM Platform screenshots:
- Autorisaties beoordelen - alle locaties
- Avebe
- Bedrijf aanmelden
- Bedrijf beoordelen
- Bedrijf bewerken
- Bezoekers aanmelden
- Contractor aanmelden - Barendrecht
- Contractor aanmelden - Rotterdam
- Contractor aanmelden Schiphol
- Dossier beoordelen
- Extra testrol Patrick
- identifier accreditatie
- Kevin test
- Medewerker Treant
- Rohit testrol
- testrol
- (and more...)

---

## Proposed Permission Matrix (Example)

| Rol                                   | Persoons-gegevens | Arbeids-gegevens | Compliance | Toegangs-rechten | View rechten |
|---------------------------------------|-------------------|------------------|------------|------------------|--------------|
| Autorisaties beoordelen - alle locaties | Volledig       | Volledig         | Volledig   | Volledig         | ✓            |
| Avebe                                 | Gedeeltelijk      | Volledig         | Volledig   | Volledig         | ✓            |
| Bedrijf aanmelden                     | Minimaal          | Volledig         | Verborgen  | Verborgen        | ✗            |
| Bedrijf beoordelen                    | Gedeeltelijk      | Volledig         | Volledig   | Samenvatting     | ✓            |
| Bezoekers aanmelden                   | Minimaal          | Verborgen        | Samenvatting | Samenvatting   | ✗            |
| Contractor aanmelden                  | Minimaal          | Gedeeltelijk     | Samenvatting | Samenvatting   | ✗            |

---

## Business Rules (Confirmed)

1. **Shared Classifications:** No shared classifications for now (context-dependent)
2. **Multiple Roles:** YES - Users can have multiple roles
3. **Permission Aggregation:** Use highest permission level across roles
4. **Default Behavior:** All categories set to "Hidden" if no role assigned
5. **View Rechten (canReveal):** Allows temporary 5-second field decryption with audit logging

---

## UI/UX Design Decisions

### Design Pattern: Table with Row per Role ✅

**Rationale:**
- YIM platform uses table-based management (see Gebruikersrollen screenshots)
- 15+ roles require vertical scrollability
- Enables comparison of permissions across all roles
- Matches mental model: "What can this role do?"

### UI Structure (Approved Concept)

```
┌─ Rol Configuratie ─────────────────────────────────────────────────────────┐
│                                                            [Instellingen ⚙️] │
├────────────────────────────────────────────────────────────────────────────┤
│ Header (Teal background #2C5F6F):                                          │
│ ┌────────────────┬──────────┬──────────┬───────────┬──────────┬─────────┐ │
│ │ Rol            │ Persoons-│ Arbeids- │ Compliance│ Toegangs-│ View    │ │
│ │                │ gegevens │ gegevens │           │ rechten  │ rechten │ │
│ ├────────────────┼──────────┼──────────┼───────────┼──────────┼─────────┤ │
│ │ Autorisaties   │[Full  ▼] │[Full  ▼] │[Full   ▼] │[Full  ▼] │   [✓]   │ │
│ │ beoordelen     │          │          │           │          │         │ │
│ ├────────────────┼──────────┼──────────┼───────────┼──────────┼─────────┤ │
│ │ Avebe          │[Part. ▼] │[Full  ▼] │[Full   ▼] │[Full  ▼] │   [✓]   │ │
│ ├────────────────┼──────────┼──────────┼───────────┼──────────┼─────────┤ │
│ │ ... (15+ more rows, scrollable)                                        │ │
│ └────────────────┴──────────┴──────────┴───────────┴──────────┴─────────┘ │
│                                                                             │
│ [Annuleren]                                            [Wijzigingen opslaan]│
└─────────────────────────────────────────────────────────────────────────────┘
```

### Style Guidelines (From Prototype)

**Colors:**
- Blue-600: #2563EB (primary actions)
- Teal: #2C5F6F (YIM platform headers)
- Gray scale for neutral elements

**Components:**
- Cards: `rounded-xl`, `border-gray-200`, `hover:border-gray-300`
- Buttons: `rounded-lg`, font-medium
- Dropdowns: Native select with 5 permission options
- Checkboxes: For "View rechten" toggle

**Modal/Page Style:**
- Fixed overlay: `bg-black bg-opacity-50`
- Card: `bg-white rounded-xl max-w-5xl`
- Sticky header with teal background
- Scrollable body for 15+ roles
- Footer with Cancel/Save actions

---

## Rejected Approaches & Why

### ❌ Modal + Dropdown per Role
**Why rejected:** Poor overview, tedious workflow (edit → save → repeat 15+ times), no comparison across roles

### ❌ Category-by-Category Editor
**Why rejected:** Doesn't match "what can this role do" mental model

### ❌ Inline Expansion Cards
**Why rejected:** Doesn't scale well with 15+ roles, loses comparison capability

---

## Data Storage (For Prototype)

**Location:** localStorage  
**Key:** `yim_role_permissions`  
**Format:**
```json
{
  "Autorisaties beoordelen - alle locaties": {
    "personal": "full",
    "employment": "full",
    "compliance": "full",
    "access": "full",
    "canReveal": true
  },
  "Avebe": {
    "personal": "partial",
    "employment": "full",
    "compliance": "full",
    "access": "full",
    "canReveal": true
  }
  // ... more roles
}
```

---

## Next Steps: Task 2 - Build Settings UI Components

### Components to Build

1. **Settings Button/Trigger**
   - Location: Header, next to "Audit Log"
   - Icon: ⚙️ Instellingen
   - Opens settings modal/page

2. **Settings Modal Component**
   - Full overlay with centered card
   - Sticky teal header
   - Scrollable body (table)
   - Footer with actions

3. **Permission Table**
   - Column headers: Rol, Persoonsgegevens, Arbeidsgegevens, Compliance, Toegangsrechten, View rechten
   - Row per role (15+ rows)
   - Dropdown per cell (5 options)
   - Checkbox for canReveal

4. **Save/Cancel Actions**
   - Cancel: Close without saving
   - Save: Update localStorage + reload role config in prototype

5. **Integration with Existing Prototype**
   - Read permissions from localStorage on load
   - Fallback to hardcoded config if not found
   - Update role selector to use dynamic config

---

## Technical Notes

**Framework:** Plain HTML/CSS/JavaScript (matching prototype)  
**Libraries:** React (via CDN), Tailwind CSS (via CDN)  
**No Backend:** All configuration stored client-side in localStorage

---

## Files & Resources

**Prototype:**
- https://yim-hiding-information-7mgy.vercel.app/

**Screenshots Analyzed:**
- Gebruikersrollen table (role management view)
- User list showing 15+ roles with varying permissions

**Reference Documents:**
- demo_yimlogin_nl_authorization_update-authorization-rule.h2d
- demo_yimlogin_nl_management_user.h2d

---

## Open Questions

1. Should we add a "Reset to Default" button?
2. Do we need role search/filter for 15+ roles?
3. Should we add validation (e.g., at least one role must have "full" access)?
4. Export/Import configuration as JSON file?

---

## Timeline

- ✅ **Task 1:** Define Settings Concept (COMPLETED)
- ⏳ **Task 2:** Build Settings UI Components (READY TO START)
- ⏸️ **Task 3:** Integration & Testing
- ⏸️ **Task 4:** Polish & Documentation

---

*Last Updated: 2026-02-05*  
*Project Lead: Kevin Rutten*  
*Platform: YIM SaaS / Axians*
