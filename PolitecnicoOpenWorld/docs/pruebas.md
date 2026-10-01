# Exam Test Report

- **Date:** 01/10/2026
- **Student / Integrant:** Tellez Giron Castro Angel Ricardo
- **Tested SHA:** `8781c7cbcea0929c90bdc8b8285d3ef9ac4bc95f` (Base SHA: `7ed325393f82872c2be94ff2ada46948efa19152`)[cite: 1]
- **Environment:** 
  - OS: Windows 10
  - Android Studio: Quail 3 | 2026.1.3 (Build AI-261.26222.65.2613.15948027)
  - Device: OPPO CPH2205 (Physical device via USB, Android 13, API 33)[cite: 1]

## Test Case Matrix

| Case | Action Performed | Observed Result | Status |
| :--- | :--- | :--- | :--- |
| **C01** | Start the application, load the Huelum vs Goya fight scenario, and let Llorona win | The scenario loads correctly; initial observation showed the win audio matched the special attack audio. | **Passed** |
| **C02** | Validation of the "Ayyyy" sound on taking damage | Corresponds to the standard hurt sound (`special_llorona_hurt`) and the new clip did not play incorrectly[cite: 1]. | **Passed** |
| **C03** | Use Llorona's special attack[cite: 1] | The usual clip plays (`special_llorona_power`)[cite: 1]. | **Passed**[cite: 1] |
| **C04** | Exit the fight using Back and re-enter[cite: 1] | The audio stopped playing and the fight functionality resumed normally[cite: 1]. | **Passed**[cite: 1] |
| **C05** | Minimize the app and return[cite: 1] | No crash occurred, and the app behaved normally upon returning[cite: 1]. | **Passed**[cite: 1] |
| **C06** | Accessibility test (maximum text size in Settings) | The menu and buttons look complete and can be tapped without issues. | **Passed** |

## Additional Evidence
- Executed host test output path: `C:\Users\LENOVO\Documents\evidencias-pow\tests-shared-rerun.txt`[cite: 1]
- **Audio Origin and License:** Audio captured directly via screen recording on a mobile device (academic / personal use for exam testing purposes).