# BWA With Mark Duplicates and BQSR #

## Description ##
New alignment workflow for latest non-TCGA projects. Per case IndelRealignment is not included in alignment workflow compared to the previous workflow. T/N paired indel realignment was performed during WXS variant calling step, but the resulting BAM is not exposed in the portal.

## Overview ##
This workflow improves the alignment quality using the tumor and normal data together to perform indel realignment and base quality recalibration. It further marks the duplicate reads within aligned data. The reason of removing case level IndelRealignment is that newer projects are submitted by batches, and GDC needs to complete alignment before all data from the same case are present.

## References ##

## External Links ##

Categories: Workflow
