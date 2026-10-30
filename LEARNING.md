# Lesson 01 · Conversation evidence

AI-drafted summary of this coaching chat on October 29, 2026, not a transcript or grade. Learner statements and coaching help are distinguished below. Approval confirms record accuracy, not independent mastery.

**Lesson:** STUDIO-001. [Specification and checks](SPEC.md) · [Issue #1](https://github.com/pb392/my-server-studio/issues/1) · [PR #2](https://github.com/pb392/my-server-studio/pull/2)

## Prediction

The learner initially said, “I'm unsure,” then chose DNS after a hint. The coach explained that DNS finds the server and Traefik chooses the container. The learner did not independently explain the corrected path before deployment; this limitation is preserved.

## Check interpretation

The learner said, “It works,” about the division-by-zero check. The coach clarified that HTTP 400 establishes rejection of that invalid input, rather than proving the entire browser journey. The learner's initial interpretation was broad; the specific explanation came from the coach.

## Browser observation

Learner-reported observation, paraphrased: the browser calculator worked, the API showed the same number as the correct calculation, and the page showed matching results. This followed the prompt to try `6 × 7`; the learner did not explicitly type the numeric result in their response. The AI's separately observed 42 results and screenshot are identified as AI evidence in SPEC.md.

## Keep decision

Learner reasoning, paraphrased: keep the deployment because the browser and API perform the calculation separately and their results match. The coach noted that agreement on one calculation is useful evidence, not proof that every possible input is correct.

## Review

On October 29, 2026, the learner reviewed the four learner excerpts and the assistance disclosure and replied, “Approve the summary for publication.” This approval preceded the summary’s first commit/push. It confirms the record’s accuracy, not independent mastery.

## AI work and help received

AI inspected the repository and selected hosting settings, prepared the local environment, proposed the scope, drafted files, ran checks, checked the public browser, and prepared GitHub evidence. The learner supplied access details, added DNS, privately authenticated and ran the prepared doctor/launch commands, and provided the observations above. With explicit approval, AI enabled the existing Mac public SSH key for this repository; the private key stayed on the Mac.

Local fast checks passed; local Docker E2E was not run. Full browser tests ran successfully in GitHub CI. The original new-launch report was exported through the supplied sanitizer. Actual results and their limits are linked from SPEC.md. This lesson used a fixed supplied image; it did not create the learner's own application release pipeline.
