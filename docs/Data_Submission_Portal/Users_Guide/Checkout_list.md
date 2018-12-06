# Checklist Before Harmonizing Data

The Harmonization step is __NOT__ an automatic process that occurs when data is uploaded to the GDC. The GDC performs batch processing of submitted data for Harmonization only after verifying that the submission is complete. 

The following tasks are required before the data can be considered complete:

1. All files are registered and have been uploaded and validated.

2. There are no invalid characters in the `submitter_id` of any node. 
The acceptable characters are alphanumeric characters [a-z, A-Z, 0-9] and `_`, `.`, `-`. Any other characters will interfer with the Harmonization workflow.

3. There are no data files with duplicate md5sums.

4. Clinical data nodes such as `demographic`, `diagnosis` and `clinical_supplement`, are linked to `case`.

5. The `read_group` node is linked to a valid node: 
    * `submitted_unaligned_reads`
    * `submitted_aligned_reads`
    * `genomic_profiles`

6. The `sample`-`analyte`-`aliquot` relationships are valid. Common problems can sometimes be:
    * `aliquot` attached to `sample` nodes of more than one type.
    * `aliquot` attached to more than one `sample` node, potentially valid but unusual.
    * `aliquot` attached to both `sample` and `analyte` nodes.

7. Each `aliquot` node is only associated with one `submitted_aligned_reads` file of the same `experimental_strategy`. 

8. The information for the `platform` is in the `read_group` node. While the subsequent information about the platform is not required, it is beneficial to also have information on:
    * `multiplex_barcode`
    * `flow_cell_barcode`
    * `lane_number`

9.  In `read_group`, the `library_strategy` should match the `library_selection`: 
    * Targeted Sequencing must be with either PCR or Hybrid Selection.
    * WXS must be with Hybrid Selection.
    * WGS must be with Random.

10.  The `target_capture_kit` property is one of the enumerations when the selected `library_strategy` is `WXS`. Errors will occur if `Not Applicable` or `Unknown` is selected.

11. Check the nodes that are related to FASTQ files. For the `submitted_unalinged_reads` node, determine that the size is correct, the files are not compressed (`.tar` or `.tar.gz`), and there is a link to `read_group`. For the `read_group` node, make sure that the `is_paired_end` is set to `true` for paired end sequencing and `false` for single end sequencing.

Once complete, clicking the `Request Submit` button will indicate to internal teams and automation system to begin data processing.