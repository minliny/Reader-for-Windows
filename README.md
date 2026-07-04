# Reader for Windows

This repository is currently not part of the active iOS / Android / HarmonyOS implementation lane.

## Current architecture role

Reader's active multi-end architecture is Contract-first Native UI Architecture:

```text
Reader UI Contract
  -> route / state / event / motion / token / view-state schema + codegen

Reader-Core-Native
  -> business source of truth

Native host apps
  -> platform reducer/coordinator + Host Adapter + Native UI
```

For the current mobile scope, active host repos are:

- `../Reader for iOS`
- `../Reader for Android`
- `../Reader for HarmonyOS`

If Windows work resumes, this repo should follow the same ownership model:

- consume Reader UI Contract generated types;
- render native Windows UI from `ViewState`;
- emit `UiEvent`;
- keep durable UI state in a Windows reducer/coordinator;
- use Reader-Core-Native for business facts;
- execute platform capability through a Windows Host Adapter.

This repo should not define a separate UI contract, fork Core business semantics, or become a shared UI runtime.
