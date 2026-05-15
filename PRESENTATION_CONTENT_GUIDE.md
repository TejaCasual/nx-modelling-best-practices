# NX Modelling Best Practices - Presentation Content Guide

## Presentation Overview
**Title:** NX Modelling Best Practices for CAD Engineers  
**Company:** Molex  
**Target Audience:** CAD Engineers  
**NX Version:** NX 2214  
**Total Slides:** 37 slides across 6 sections

---

## SECTION 1: OVERVIEW & INTRODUCTION (Slides 1-3)

### Slide 1: Title Slide
- **Title:** NX Modelling Best Practices
- **Subtitle:** For CAD Engineers using Molex Standards
- **Company:** Molex
- **Date:** May 2026
- **NX Version:** 2214
- **Image:** Molex Logo + NX Logo + Automotive connector imagery

### Slide 2: What You'll Learn Today
- Content:
  - How to create effective models in NX
  - Assembly best practices and strategies
  - Professional drafting techniques
  - Teamcenter integration workflows
  - Engineering vs. Customer drawing requirements
  - Object type standards (Product Part & Mech Design)
- Visual: Bullet points with icons for each topic

### Slide 3: Why Standardization Matters
- Benefits:
  - Ensures consistency across projects
  - Improves collaboration in Teamcenter
  - Reduces errors and rework
  - Accelerates design process
  - Better documentation for customers
  - Facilitates design changes
- Visual: Flowchart showing data flow from modeling → assembly → drafting → Teamcenter

---

## SECTION 2: HOW TO MODEL (Slides 4-10)

### Slide 4: Part Fundamentals - Object Type Setup
- **Object Type:** "Product Part"
- Key Points:
  - Set object type at file creation
  - Enables tracking in Teamcenter
  - Defines manufacturing workflow
  - Required for BOM generation
- Setup Steps:
  1. Create New Part File → Advanced → Select "Product Part"
  2. Set standard naming convention
  3. Define working directory structure
- Visual: Screenshot of part creation dialog

### Slide 5: Sketching Best Practices
- Sketch Strategy:
  - One sketch per feature when possible
  - Fully constrain all sketches
  - Use reference geometry for complex parts
  - Name sketches descriptively
  - Lock critical dimensions
- Constraint Methods:
  - Geometric constraints (tangent, perpendicular, parallel)
  - Dimensional constraints
  - Driven dimensions for reference
- Visual: Examples of well-constrained vs. under-constrained sketches

### Slide 6: Feature Creation Strategy
- Recommended Feature Order:
  1. Base features (pads, pockets)
  2. Holes (counterbore, tapped)
  3. Fillets and chamfers (last)
  4. Pattern features
- Best Practices:
  - Keep features simple and parametric
  - Avoid self-intersecting geometry
  - Use reference planes for complex parts
  - Reuse sketches through mirroring
- Visual: Feature tree example with proper organization

### Slide 7: Parametric Design & Dimensions
- Parameter Management:
  - Create design parameters for key dimensions
  - Use expressions for driven dimensions
  - Link model dimensions to specifications
  - Document parameter meanings
- Benefits:
  - Easy design modifications
  - Consistency across variants
  - Automated BOM updates
- Visual: Parameters dialog box example

### Slide 8: Advanced Modeling Techniques
- Surface Modeling:
  - When to use surfaces vs. solids
  - Basic surface creation
  - Stitching and knitting surfaces
- Feature Reuse:
  - Mirroring features
  - Pattern and instance
  - Copy body methods
- Visualization Tips:
  - Color coding for different bodies
  - Layer organization
- Visual: Complex part example with surfaces and solids

### Slide 9: Teamcenter Integration - Part Level
- Workflow:
  1. Create part in NX (Product Part object type)
  2. Save locally with naming convention
  3. Check-in to Teamcenter
  4. Set revision state (Working → Released)
  5. Link related data (drawings, BOMs)
- Naming Convention: [Component_Type]_[Description]_[Version]
  - Example: CONN_USB_A_V1
- File Management:
  - One part file per component
  - Organize in Teamcenter folders by project
- Visual: Teamcenter folder structure diagram

### Slide 10: Best Practices Summary - Modeling
- ✓ Always use "Product Part" object type
- ✓ Fully constrain sketches before feature creation
- ✓ Maintain clean feature tree
- ✓ Use meaningful names for features and sketches
- ✓ Create parametric designs for flexibility
- ✓ Document complex geometry
- ✗ Avoid: Suppressing features, duplicate geometry, orphaned sketches
- Visual: Checklist format with checkmarks and X marks

---

## SECTION 3: HOW TO ASSEMBLE (Slides 11-18)

### Slide 11: Assembly Structure & Hierarchy
- Assembly Concepts:
  - Top-level assembly (main structure)
  - Sub-assemblies (logical grouping)
  - Components (individual parts)
- Hierarchy Best Practices:
  - Keep assemblies under 500 parts
  - Use sub-assemblies for maintenance
  - Group by function or location
  - Avoid circular references
- Visual: Organizational tree diagram showing multi-level assembly

### Slide 12: Assembly Object Type & Setup
- **Object Type:** "Product Part" (assemblies are also Product Parts)
- Assembly File Naming:
  - ASM_[System]_[Description]_[Version]
  - Example: ASM_CONNECTOR_HOUSING_V2
- Initial Setup:
  1. Create Assembly file
  2. Set properties in Teamcenter
  3. Create coordinate system
  4. Define assembly context
- Visual: Assembly creation workflow

### Slide 13: Constraint Types & Application
- Key Constraint Types:
  - **Coincident:** Align faces, planes, or edges
  - **Perpendicular:** Orient at 90°
  - **Parallel:** Maintain alignment
  - **Distance:** Set gaps or clearances
  - **Angle:** Define angular relationships
  - **Mate/Align:** Surface-to-surface contact
  - **Contact:** Physical constraints
- Constraint Strategy:
  - Use minimum constraints needed
  - Avoid redundant constraints (over-constraining)
  - Document constraint rationale
- Visual: Examples of each constraint type with visual indicators

### Slide 14: Component Placement Workflow
- Step-by-Step Process:
  1. Insert component reference
  2. Apply positioning constraints
  3. Verify collision-free placement
  4. Save component state
  5. Update assembly BOM
- Component Reference Types:
  - Insert from existing file
  - Create instance
  - Link external component
- Visual: Step-by-step assembly workflow with screenshots

### Slide 15: Sub-Assembly Strategy
- When to Use Sub-Assemblies:
  - Logical functional grouping
  - Improved file performance
  - Easier modifications
  - Reusable component groups
- Sub-Assembly Naming:
  - Include level indicator: ASM_LEVEL1_LEVEL2_[Name]
  - Example: ASM_CONNECTOR_HOUSING_SHELL_V1
- Benefits:
  - Faster assembly loads
  - Better team collaboration
  - Clear component ownership
- Visual: Assembly tree showing multiple sub-assembly levels

### Slide 16: BOM Generation & Structure
- BOM Basics:
  - Automatically generated from assembly structure
  - Links to component properties
  - Reflects design hierarchy
- BOM Content by Level:
  - Top Assembly: All sub-assemblies + fasteners
  - Sub-Assembly: Component parts only
  - Part Level: Geometry details
- BOM Export:
  - CSV format for spreadsheets
  - PDF for documentation
  - Integration with Teamcenter
- Visual: Sample BOM table showing hierarchy and part numbers

### Slide 17: Assembly Verification & Conflict Detection
- Verification Checks:
  1. Collision detection (interferences)
  2. Constraint satisfaction
  3. Part alignment verification
  4. Mass and center of gravity check
  5. Assembly completeness
- Tools Available:
  - Assemblies → Check Interference
  - Bill of Materials → Verify
  - Assembly Compare
- Documentation:
  - Create verification report
  - Flag issues in Teamcenter
- Visual: Example of collision detection report

### Slide 18: Best Practices Summary - Assembly
- ✓ Use clear hierarchy (top-level → sub-assemblies → parts)
- ✓ Minimize number of constraints per component
- ✓ Document assembly logic and constraints
- ✓ Verify collisions before release
- ✓ Use sub-assemblies for complex designs (>100 parts)
- ✓ Maintain consistent naming conventions
- ✗ Avoid: Over-constraining, excessive sub-levels, unsaved constraints
- Visual: Checklist format with best practices

---

## SECTION 4: HOW TO DRAFT (Slides 19-27)

### Slide 19: Drawing Basics & Object Type
- **Object Type:** "Mech Design" (for all drawings)
- Drawing File Naming:
  - DRW_[Part/Assembly]_[View Type]_[Version]
  - Example: DRW_CONNECTOR_HOUSING_ASSEMBLY_V1
- Drawing Sheet Setup:
  - Template with company standard border
  - Titleblock with revision information
  - Predefined layer structure
  - Standard annotation styles
- Visual: Sample drawing template with Molex branding

### Slide 20: View Creation & Management
- Standard View Types:
  - Front, Top, Right Side
  - Isometric (3D view)
  - Detail views for close-ups
  - Section views for internal details
- View Placement:
  - Logical arrangement on sheet
  - Proper spacing between views
  - Aligned with engineering standards
  - Scale appropriate to sheet size
- Layer Organization:
  - Geometry (visible edges)
  - Hidden lines (dashed)
  - Dimensions
  - Annotations
  - Center lines
- Visual: Multi-view drawing example showing proper layout

### Slide 21: Engineering Drawing - Detailed BOM
- **Purpose:** Complete technical specification for manufacturing
- **Content Requirements:**
  - Every component with full part number
  - Item numbers linked to assembly views
  - Quantities and references
  - Material specifications
  - Special notes and callouts
  - Revision information
- **Level of Detail:**
  - All sub-assemblies listed
  - All individual fasteners
  - Optional parts clearly marked
  - Supplier information when required
- Table Structure:
  - Item Number
  - Part/Assembly Number
  - Description
  - Quantity
  - Material
  - Notes/Reference
- Visual: Example of detailed BOM table for engineering drawing

### Slide 22: Customer Drawing - Simplified BOM
- **Purpose:** High-level overview for customer understanding
- **Content Requirements:**
  - Main assemblies only
  - Visible connector details
  - Cable routing and connections
  - Major components
  - Limited technical detail
- **Level of Detail:**
  - Connector types (USB, Ethernet, etc.)
  - Cable sizes and types
  - Optional modules
  - Interface information
  - Reference callouts
- Table Structure:
  - Item Number
  - Description (simple)
  - Quantity
  - Key Notes (compatibility, features)
- Visual: Example of simplified customer-facing BOM

### Slide 23: Dimension & Tolerance Application
- Dimensioning Standards:
  - ISO 13715 for tolerances
  - GD&T (Geometric Dimensioning & Tolerancing)
  - Critical vs. reference dimensions
- Dimension Placement:
  - Closest to view
  - No crossing dimension lines
  - Proper spacing
  - Clear leader lines
- Tolerance Notation:
  - Positional tolerances for alignment
  - Runout for cylindrical features
  - Profile tolerances for surfaces
  - General notes for standards
- Special Callouts:
  - Material specifications
  - Heat treatment requirements
  - Surface finish
- Visual: Detailed drawing with dimensions and tolerances

### Slide 24: Engineering vs. Customer Drawing Comparison
- **Engineering Drawing:**
  - ALL component details
  - Every hole, thread, surface
  - Complete tolerance stack-up
  - Manufacturing-ready specifications
  - Complex assembly cross-sections
  - Internal connector pin layouts
  - Cable internal routing
- **Customer Drawing:**
  - External appearance only
  - Key connector specifications
  - Cable types and lengths
  - Overall dimensions for mounting
  - High-level assembly view
  - Interface specifications
  - Molex connector product numbers
  - Cable/connector compatibility matrix
- Visual: Side-by-side comparison of engineering and customer drawings

### Slide 25: Annotation & Notes Best Practices
- Technical Notes:
  - Clearly reference items in view
  - Use consistent terminology
  - Specify manufacturing processes
  - List assembly instructions
- Customer-Specific Notes:
  - Connector compatibility information
  - Cable gauge and type
  - Pinout diagrams (simplified)
  - Interface requirements
  - Installation guidelines
- Formatting:
  - Consistent font and size
  - Organized by category
  - Numbered for cross-reference
  - Easy to translate if needed
- Visual: Example drawing with properly formatted annotations

### Slide 26: Teamcenter Drawing Management
- Drawing Check-In Workflow:
  1. Create drawing with Mech Design object type
  2. Link to source part/assembly
  3. Review for completeness
  4. Check-in to Teamcenter
  5. Set revision state
  6. Link to related part data
- Version Control:
  - Track drawing revisions
  - Link ECR (Engineering Change Requests)
  - Maintain history for traceability
  - Archive obsolete versions
- Drawing Release:
  - Engineering approval
  - Customer approval (if required)
  - Mark as Released in Teamcenter
  - Notify relevant teams
- Visual: Teamcenter drawing workflow diagram

### Slide 27: Best Practices Summary - Drawing
- ✓ Always use "Mech Design" object type
- ✓ Engineering drawings: Complete technical detail
- ✓ Customer drawings: Simplified, customer-focused
- ✓ Clear BOM structure reflecting assembly hierarchy
- ✓ Include all tolerances and GD&T specifications
- ✓ Consistent annotation and note formatting
- ✓ Proper dimension placement and spacing
- ✗ Avoid: Cluttered views, inconsistent scales, missing tolerances, over-detailed customer drawings
- Visual: Checklist format

---

## SECTION 5: TEAMCENTER INTEGRATION (Slides 28-35)

### Slide 28: Teamcenter Workflow Overview
- **What is Teamcenter?**
  - Product Lifecycle Management (PLM) system
  - Central repository for all design data
  - Version and revision control
  - Collaboration platform
  - Change management
- Benefits:
  - Single source of truth
  - Concurrent engineering support
  - Audit trail and traceability
  - Automated workflows
  - Integration with manufacturing
- Visual: Teamcenter system architecture diagram

### Slide 29: File Management & Organization
- Folder Structure:
  ```
  Project_Name/
  ├── Parts/
  │   ├── Connectors/
  │   ├── Cables/
  │   ├── Housings/
  │   └── Hardware/
  ├── Assemblies/
  │   ├── Sub_Assemblies/
  │   └── Top_Level/
  ├── Drawings/
  │   ├── Engineering/
  │   └── Customer/
  └── BOMs/
  ```
- Naming Convention Rules:
  - Consistent naming across all files
  - Version numbering scheme (V1, V2, etc.)
  - Date stamps for revisions
  - Project code prefix
- Visual: Folder structure diagram

### Slide 30: Check-In & Check-Out Process
- **Check-Out:**
  - Select file from Teamcenter
  - Right-click → Check Out
  - File becomes editable locally
  - Others see as "checked out"
- **Working Locally:**
  - Open in NX
  - Make modifications
  - Save regularly
  - Maintain version naming
- **Check-In:**
  1. Save all changes
  2. Right-click file → Check In
  3. Add revision comments
  4. Select "Release" status if ready
  5. Notify team if needed
- Conflict Resolution:
  - Merge conflicts manually
  - Communicate with team
  - Document all changes
- Visual: Check-in/Check-out workflow diagram

### Slide 31: Revision & Release Management
- Revision States:
  - **Working:** In development, not finalized
  - **Released:** Approved for manufacturing
  - **Obsolete:** No longer used
  - **Superseded:** Replaced by newer version
- Release Process:
  1. Complete design review
  2. All drawing/part checks passed
  3. Engineering approval
  4. Set state to "Released"
  5. Document release notes
- Version Control:
  - Each significant change = new version
  - Maintain revision history
  - Link changes to ECRs (Engineering Change Requests)
  - Archive previous versions
- Visual: Revision status diagram with transitions

### Slide 32: Data Relations & Links
- Linking Parts to Drawings:
  - Drawing → Source Part link
  - BOM → Assembly structure
  - Revision → Related revisions
- Cross-References:
  - Part to related assemblies
  - Assembly to sub-assemblies
  - Drawing to corresponding model
  - Change notices to affected files
- Impact Analysis:
  - View dependent documents
  - Identify affected components
  - Propagate changes systematically
- Visual: Relationship diagram showing interconnected data

### Slide 33: Collaboration Features
- Team Sharing:
  - View permissions (read-only)
  - Edit permissions (checked out)
  - Approval workflows
  - Comment and annotation
- Concurrent Engineering:
  - Multiple users on same project
  - Conflict detection
  - Change notifications
  - Task assignment
- Communication:
  - Embedded notes in files
  - Change summaries
  - Notification alerts
  - Document history tracking
- Visual: Collaboration interface example

### Slide 34: Change Management & ECR Process
- Engineering Change Request (ECR):
  - Document design changes
  - Impact assessment
  - Approval workflow
  - Implementation tracking
- ECR Contents:
  - Description of change
  - Reason for change
  - Affected parts/drawings
  - Revised files
  - Implementation date
- Workflow:
  1. Submit ECR with details
  2. Engineering review
  3. Manufacturing impact assessment
  4. Management approval
  5. Implementation and documentation
  6. Verification and closure
- Visual: ECR process flowchart

### Slide 35: Teamcenter Best Practices Summary
- ✓ Always organize files in proper folder structure
- ✓ Use consistent naming conventions
- ✓ Check out before editing, check in with comments
- ✓ Set appropriate revision states
- ✓ Link all related documents
- ✓ Notify team of major changes
- ✓ Document all modifications
- ✓ Archive obsolete versions
- ✗ Avoid: Working outside Teamcenter, inconsistent naming, untracked changes, orphaned files
- Visual: Best practices checklist

---

## SECTION 6: CONCLUSION (Slides 36-37)

### Slide 36: Key Takeaways
- **Modeling:** Use Product Part object type, create parametric designs, maintain clean geometry
- **Assembly:** Build logical hierarchies, use minimum constraints, verify collisions
- **Drawing:** Engineering drawings (detailed BOM) vs. Customer drawings (simplified), use Mech Design object type
- **Teamcenter:** Central repository, version control, change management, team collaboration
- **Standards:** Consistency, documentation, and traceability
- Benefits of Following Standards:
  - Faster design cycles
  - Better team communication
  - Higher quality deliverables
  - Reduced errors and rework
  - Easier maintenance and updates
- Visual: Summary infographic with key icons

### Slide 37: Quick Reference Guide
- **Part Setup:** New Part → Advanced → Product Part
- **Assembly Setup:** New Assembly → Product Part (assemblies)
- **Drawing Setup:** New Drawing → Mech Design
- **Naming Template:**
  - Parts: CONN_[Description]_V[#]
  - Assemblies: ASM_[System]_[Description]_V[#]
  - Drawings: DRW_[Name]_[Type]_V[#]
- **Essential Constraints:** Coincident, Perpendicular, Parallel, Distance, Angle
- **BOM Types:**
  - Engineering: All components, detailed
  - Customer: High-level, visible connectors/cables only
- **Teamcenter Workflow:** Check-out → Edit → Check-in → Review → Release
- **Contact Information:** Links to Molex CAD support, training resources, design standards documentation
- Visual: Quick reference card format

---

## Image Recommendations

1. **Slide 1 (Title):** Molex logo, NX 2214 logo, automotive connectors (USB, Ethernet, power connectors)
2. **Slide 4:** Screenshot of NX part creation dialog with "Product Part" option highlighted
3. **Slide 5:** Examples of constrained vs. under-constrained sketches
4. **Slide 6:** Typical feature tree showing organized structure
5. **Slide 8:** Complex model with surfaces and parametric features
6. **Slide 11:** Assembly hierarchy diagram (tree structure)
7. **Slide 13:** Visual examples of different constraint types
8. **Slide 14:** Step-by-step component placement sequence
9. **Slide 20:** Multi-view engineering drawing with proper layout
10. **Slide 21:** Detailed BOM table from engineering drawing
11. **Slide 22:** Simplified BOM from customer drawing
12. **Slide 24:** Side-by-side comparison of engineering and customer drawings
13. **Slide 24 (special):** Molex automotive connectors - USB Type-C, RJ45, power connectors
14. **Slide 28:** Teamcenter system architecture
15. **Slide 29:** Folder structure hierarchy visualization
16. **Slide 30:** Check-in/Check-out workflow diagram
17. **Slide 31:** Revision state transitions
18. **Slide 32:** Data relationship diagram
19. **Slide 36:** Summary infographic with key topics

---

## Notes for CAD Engineers

- Refer to company CAD standards document for detailed guidelines
- Teamcenter training: Contact your system administrator
- Questions about part standards: Consult design engineering lead
- Molex connector specifications available on molex.com
- Keep presentations updated with latest NX 2214 features
- Provide hands-on training sessions with real project examples
- Create template files for standardized part/assembly/drawing creation

---

**Document Created:** May 15, 2026  
**For:** Molex CAD Engineering Team  
**NX Version:** 2214  
**Presentation Format:** PowerPoint (.pptx)
