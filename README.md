# Regulatory Change Impact — learner starter

## Get a working copy

Public starter: [GitRollTraining/regulatory-compliance](https://github.com/GitRollTraining/regulatory-compliance). Use a Git-enabled terminal in the supplied Agent Skills-capable coding environment:

```bash
git clone https://github.com/GitRollTraining/regulatory-compliance.git
cd regulatory-compliance
```

Read this README from that working-copy root. The starter supplies instructions and inputs; you create the Skill and its outputs. Keep credentials out of the repository. The facilitator supplies the supported runtime, read-only source access and assessed submission/capture route; report missing setup to that owner. The public starter is not an assigned submission destination. For a pre-S3 authoring trial, the designer selects the authorized Agent test identity, isolated workspace and test submission/capture route; no human learner or Classroom assignment is needed for that test.

Interview entry: [Compliance and Operations Manager](https://work-sim-alpha.catalyte.ai/s/project-b-regulatory-compliance). This starter contains the assignment, source catalog, public schema and complete legal baseline. Before an assessed run, the facilitator must verify your access to the current view-only company sources, interview identity/export, coding-session capture and assigned submission repository. Report a missing binding to the facilitator; do not invent links or reviewer replies.

Read the provided assignment, source catalog, public schema and full official legal baseline. Interview the Compliance and Operations Manager yourself, then build the `regulatory-change-impact-brief` Agent Skill and its end-to-end command. This scaffold supplies no implementation or expected findings.

Given files: [assignment](scenario-and-task.md), [public schema](snapshot.schema.json), [source catalog](inputs/source-catalog.md), and [legal source manifest](inputs/legal/source-manifest.json) with its three full source texts. All nine source entry links are already in the catalog; interview for their meaning, business context and authority boundaries. The baseline review date is 26 August 2026; actual source retrieval dates stay separate. From this starter directory run this optional environment smoke:

```bash
python3 -c 'import hashlib,json,pathlib; s=json.loads(pathlib.Path("snapshot.schema.json").read_text()); assert s["properties"]["sequence"]["maximum"]==7; assert pathlib.Path("scenario-and-task.md").is_file(); assert pathlib.Path("inputs/source-catalog.md").is_file(); m=json.loads(pathlib.Path("inputs/legal/source-manifest.json").read_text()); assert len(m["documents"])==3; assert all("sha256:"+hashlib.sha256((pathlib.Path("inputs/legal")/d["file"]).read_bytes()).hexdigest()==d["sha256"] for d in m["documents"]); print("Starter inputs readable; business workflow not implemented")'
```

Each run uses the intact supplied case-date legal baseline and reads current remote company records; preserve any legal refresh separately and do not claim an update without actual version evidence. A missing/corrupt baseline is a facilitator preparation defect.

The optional smoke requires Python 3 with its standard library only. It reads the named local files, checks the seven-stage upper bound and verifies the three legal text hashes; expect `Starter inputs readable; business workflow not implemented`. A missing file, malformed JSON, wrong stage bound or mismatched text hash must exit nonzero. Report damaged supplied inputs to the facilitator. This does not validate a learner snapshot, legal interpretation, live access or Skill-host capability. Your solution may use another supported language.

JSON uses quoted field names, arrays for lists and unquoted `null` for unknown values. The public schema describes required fields, types and allowed states. The assignment supplies the stage meanings and additional cross-file rules. The facilitator verifies the interview recording/export and assigned submission destination before the assessed run.

You create the Skill implementation and required deliverables listed in the assignment. Preserve source captures, all seven snapshots and prior-run evidence when correcting/retrying; produce the impact CSV, brief and draft ICS. Partial/blocked outputs disclose their scope and pending review. All sources are read-only; no final legal advice, source edits, live calendar changes, activation or incident closure.

The facilitator provides the actual supported identity/session-capture route. Keep attributable project decisions there; an invented transcript is not evidence. Submit the repository containing the Skill and actual outputs to the assigned destination, excluding credentials and temporary caches. Trainer references, private prompts and expected answers are not part of this starter.
