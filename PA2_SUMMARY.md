# PA2 Assignment Roadmap

This repository is for **CSC 4200/5200 Programming Assignment 2 (PA2)**: implement **ETP-T**, a reliable, connection-oriented transport protocol over UDP. Use the official PA2 brief and specification as the authority for exact protocol requirements; this file is a practical checklist of the work and submission pieces reflected in this repository.

## Steps

1. **Read the assignment materials.** Review the PA2 brief and protocol specification, especially segment format and validation, reliability, timers, connection setup/teardown, and the measurement requirements. Note the repository owner's relay profile; the README includes the `etpt_relay.py --show-profile OWNER` command.

2. **Understand the starter code and interfaces.** Read `include/etpt.h`, `include/transport.h`, and the files in `src/`. Identify the segment codec, transport implementation, and sender/receiver command-line programs. Keep the implementation aligned with the supplied interfaces and specification.

3. **Implement and build the transport.** Complete segment encoding/decoding and checksum handling, sending and receiving, cumulative acknowledgements, the sending window and Go-Back-N retransmission behavior, RTT/RTO estimation, and SYN/FIN connection handling. Build with `make build` and resolve compiler errors and warnings.

4. **Check behavior and debug.** Run `make check` against the course self-check. Investigate failures and repeat checks as you make fixes. Add or run focused tests for cases required by the specification, such as corrupted or out-of-order segments, lost ACKs, retransmissions, and connection-close behavior.

5. **Run an end-to-end transfer.** Start the receiver, relay, and sender as shown in `README.md`. Confirm the output file matches the input. Capture a transfer through the relay and save the required capture as `evidence/pa2-capture.pcap`.

6. **Measure performance.** Run `make measure` for the repository owner's profile. Preserve the generated `evidence/measurements.csv` and `evidence/throughput.svg`. Use the profile and results to fill the facts block and answer the questions in `evidence/ANALYSIS.md`.

7. **Document the implementation and results.** Replace the prompts in `DESIGN.md` with an accurate description of the submitted code. Complete `evidence/ANALYSIS.md` using your own capture and measurements. Finish `README.md` with build/run details, self-check results and known issues, team contributions, file descriptions, and author signatures.

8. **Disclose AI use and prepare the submission.** Complete `AI_USE.md` truthfully for all substantive AI interactions. Review that the source, documentation, and evidence are your team's work and that every author can explain the submission. Record the submitted commit SHA in the README and submit it as directed by the course.

## Main deliverables

- ETP-T sender and receiver implementation in `src/`, following the interfaces in `include/`.
- Completed `README.md` and `DESIGN.md`.
- Completed `AI_USE.md` disclosure.
- `evidence/pa2-capture.pcap`, `evidence/measurements.csv`, and `evidence/throughput.svg`.
- Completed `evidence/ANALYSIS.md` with measured values and answers.

## Useful commands

```sh
make build
make check
make measure
```

For the end-to-end run commands and relay setup, see the Build and run section in `README.md`.
