# Character State Schema

Use this schema for a human or agent-operated character at one scene boundary.

```yaml
character_id: ""
continuity_id: ""
scene_id: ""
time: ""
location: ""

public_identity:
  names: []
  roles: []
  affiliations: []

body_state:
  health: ""
  energy: ""
  tension: ""
  movement_constraints: []

current_want: ""
current_fear: ""
operative_center: ""

knowledge:
  observed: []
  inferred: []
  believed: []
  false_or_stale: []
  unknown_to_character: [] # narrator-only

relationships:
  - body_id: ""
    trust: ""
    obligation: ""
    conflict: ""
    last_material_change: ""

resources:
  material: []
  information: []
  authority: []
  social: []

membranes:
  can_perceive: []
  can_access: []
  can_change: []
  can_refuse: []
  cannot_cross: []

active_mirrors:
  - mirror: ""
    trust_level: ""
    blind_spot: ""

private_primes: []
open_actions: []
forbidden_actions: []
last_choice: ""
residue: []
```

## Separation rules

- `observed` stores what entered the character's available field.
- `inferred` stores conclusions drawn from observations.
- `believed` may include unsupported or inherited narratives.
- `unknown_to_character` remains narrator-only and must never be included in the character agent prompt.
- `operative_center` is a current hypothesis, not permanent essence.
- relationship values require event notes; unsupported scalar scores should not govern prose.

## Update rule

State changes only after a settled event, deliberate internal reweighting, or declared time passage. Do not rewrite prior state to make the current scene feel inevitable.
