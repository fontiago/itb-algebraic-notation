# Into the Breach Notation

### A guide to textually and visually notating moves in Into the Breach

## Text

As per update 1.0.16, ITB has a native grid overlay ("Grid Coordinates" in the options) so those coordinates are what's used here. Text notation should ideally exist alongside a screenshot to explain what is happening, and any pilot-specific abilities used should be noted preceding the notation itself. I've based this on algebraic chess notation.

### Basic rules

- Your unit is designated by the tile it starts the turn in.
- Unit **movement** is designated by an **initial tile** and an **ending tile** with a **hyphen** inbetween.
  - Example: `A2-B3` (I move my unit that's in *A2* to *B3*.)
- Unit abilities are designated by an **initial tile** and a **target tile** with an **x** inbetween. Projectile and artillery weapons need no differentiation.
  - Melee example: `C5xD5` (My unit in *C5* attacks tile *D5*.)
  - Projectile example: `C5xE5` (My unit in *C5* attacks tile *E5* with a projectile.)
  - Artillery example: `C5xC1` (My unit in *C5* attacks tile *C1* with artillery.)
- Each action should be listed in the order committed on **new lines**, or for brevity, with a semicolon between.
  - Example:
  
      ```
      A3-C3
      C3xC4
          1xC4
      ```
  - Or: `A3-C3; C3xC4`
- **Results** of an action are listed under the action on **indented new lines**, or for brevity, in **parentheses** after the action with semicolons between each result.
  - **Damage** is indicated as the **amount of damage** and the **tile it is applied to** with an **x** inbetween.
  - **Deaths** are indicated as the **tile of the unit that dies** with an **x** preceding it.
  - A **push** is indicated simply as a move. Pushed tiles that have no unit are omitted. If a push results in a collision ("bump") or environmental death, put the results of that collision in a nested indent or set of parentheses.
  - A **bump** is assumed to actually move neither of the occupants.
  - An **environmental death** is designated by the tile it's located on, not the inital tile of the unit that was pushed onto it.
      - Example (semicolons for readability): My Artillery Mech in *C5* attacks *C3*, which does 1 damage to *C3*; pushes *B3* to *A3*; pushes *C2* (a non-flying unit) to *C1* (a water space), killing it; and pushes *D3* to *E3* (which contains a unit already), dealing 1 bump damage to both.

      ```
      C5xC3
          1xC3
          B3-A3
          C2-C1
              xC1
          D3-E3
              1xD3
              1xE3
      ```
      - Or: `C5xC3 (1xC3; B3-A3; C2-C1 (xC1); D3-E3 (1xD3; 1xE3))`
