- #[[Backup Pareto Practice]] #[[Infra]] #[[Self-hosted-Budgeting-App]]
- # What to test?
	- | Property | Mechanism | Certainty |
	  | ---- | ---- | ---- |
	  | Archive not corrupted | tar read | High |
	  | Files fully restorable | extraction | High |
	  | Files not silently altered | sha256 | High |
	  | DB structurally valid | SQLite pragma | High |
-