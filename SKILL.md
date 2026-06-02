---
name: court-filing-material-check
description: Check and prepare Chinese court online litigation filing materials before upload. Use when Codex helps with 中国法院网上立案、一站式诉讼服务平台、民事一审/二审立案、材料分类、上传材料选择、补正材料核对, especially to verify complaint, party identity proof, attorney authorization, law firm letter, lawyer certificate copy, evidence bundle, and service address confirmation before any filing submission.
---

# Court Filing Material Check

Use this skill before uploading or submitting materials on a Chinese court online filing platform.

## Core Rule

Do not treat a document as acceptable merely because its name is similar. Verify the required legal effect of the file:

- Signed or sealed materials must be uploaded as signed/sealed PDFs or scanned images.
- Draft Word files (`.doc`, `.docx`) are not substitutes for signed or sealed filing materials.
- Natural-person identity proof should be an ID card scan/photo, not a household register, unless the court specifically asks for household registration material.

## Workflow

1. Classify the case type from the file set and pleadings.
   - 民事一审: look for 民事起诉状, first-instance court, cause of action, plaintiff/defendant structure.
   - 民事二审: look for 上诉状, first-instance judgment/ruling, appellant/appellee structure.
   - Ask the user when the file set is mixed, already filed, or unclear.

2. Identify the filing platform material categories before upload.
   - 起诉状/上诉状
   - 当事人身份证明
   - 委托代理人委托手续和身份材料
   - 证据目录及证据材料
   - 送达地址确认书
   - Other court-specific required categories

3. Build an upload candidate list.
   - Prefer PDFs or scanned images for signed/sealed materials.
   - Prefer compressed PDF evidence bundles when upload size is a practical issue.
   - Keep a separate "needs user confirmation" list for missing, unsigned, unsealed, or ambiguous files.

4. Stop before final submission and ask for explicit confirmation.
   - Uploading confirmed files is allowed after user confirmation.
   - Final submission requires a separate explicit user confirmation.

## Material Rules

### Complaint

For 民事一审, upload the actual civil complaint used for filing.

Accept:
- Signed/sealed PDF complaint when available.
- Word complaint only when the platform accepts it and the user confirms it is intended for filing.

Do not select 要素式立案 if the user says not to use 要素式.

### Party Identity Proof

For a natural person:
- Require resident ID card front and back scan/photo/PDF.
- Do not use 户口本 as the ordinary substitute for 身份证明.
- If only a household register is found, flag it and ask for the ID card.

For a company or organization:
- Use business license, enterprise credit report, unified social credit code proof, or other accepted registration proof.

### Attorney Authorization Materials

For 委托代理人委托手续和身份材料, require all applicable parts:

- 授权委托书: PDF or scan with client signature/handprint/stamp.
- 律师事务所函/所函: PDF or scan with law firm seal.
- 律师证复印件/律师执业证复印件: scan/PDF/image.

Do not upload unsigned/unsealed `.doc` or `.docx` drafts as the final authorization material unless the user explicitly says the court accepts them for this specific filing.

If the platform groups the category into one upload area, upload all three files together.

### Evidence

Evidence should include both:
- 证据目录
- 证据材料

If there is a combined PDF such as `证据清单+证据.pdf`, prefer it. If the file is too large, look for a compressed version and tell the user which one will be uploaded.

### Service Address Confirmation

Upload the signed/confirmed service address confirmation form when available. If it contains phone numbers, it may be used to fill litigation contact fields only when the user confirms or the context clearly identifies it as the litigation contact number.

## Field-Fill Cautions

- 标的金额 often accepts only two decimal places. Round monetary claims to two decimals when the platform rejects more precision.
- Do not invent missing phone numbers, ID numbers, representative information, or lawyer certificate numbers.
- If a required corporate representative phone number is unavailable, ask the user whether to use a litigation contact number as a placeholder.
- Preserve the user's instruction about whether to agree to mediation; ask before choosing 同意/不同意先行调解.

## Pre-Upload Checklist

Before uploading, report concise findings:

- Case type and court
- Cause of action
- File selected for each material category
- Any material that is missing, unsigned, unsealed, or not in the expected format
- Any user decisions needed before upload

For natural-person identity proof and attorney authorization materials, always explicitly verify:

- 身份证明 is ID card, not household register.
- 授权委托书 is signed PDF/scan.
- 所函 is sealed PDF/scan.
- 律师证复印件 is included.

## Submission Boundary

Never final-submit a filing just because earlier uploads were approved. Stop on the preview/submit page and ask the user to confirm final submission. If the user personally clicks submit, inspect the resulting page and report whether it says 提交成功 or shows a correction prompt.
