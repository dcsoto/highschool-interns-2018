.. Friday activities

Friday activities
=================

10:00 - 12:00 Quality check of BAC clone

12:00 - 13:00 Lunch break

13:00 - 15:00 Comparing BAC clone to the human genome

1. Quality control of BAC clone
-------------------------------

On Wednesday, we learned about Linux commands, fastq format to store DNA sequences and quality control.

Today, we will apply all this knwoledge to analyze the BAC clone sequences that you obtained last week.

**Activity 1:** Together, review for 15 minutes the BAC clone sequencing process that you did last week. Then, prepare a 5 minutes talk using the board to explain the process. Both should talk!

**Activity 2:** Let's apply what we learned this Wednesday!
- Access the cluster (hint: ``ssh``)
- Go to your personal folder (hint: ``cd``)
- Download the data contained in this url: https://osf.io/3q9m2/download (hint: ``wget``)
- Check that you have a new ``fastq`` file in your folder (hint: ``ls``)

Excellent! Now we have the data that you sequenced last week! To analyze its quality we will use a tool called NanoPlot.

Let's check the quality of the sequences.

**Activity 3:** Use the following commands

.. code-block:: bash

   NanoPlot --fastq minion_ch17.fastq -o qc_plots

Go to the qc_plot folder (hint: you can use `cd`) and check the files inside (hint: you can use `ls`). What do you see?

A copy of the files can be downloaded from  the following address: https://osf.io/gpkbm/. Download this files into your computer and look at them

2. Mapping BAC clone sequences to the human genome
--------------------------------------------------

Go inside the cluster again and then move to your folder.

**Activity 4:** Run the following command:

.. code-block:: bash

   minimap2 -ax map-ont -L /share/dennislab/databases/assemblies/GRCh38/hg38.noalt.mmi minion_ch17.fastq > minion_ch17.sam

We will have to wait a little bit. The software is performing a mapping procedure. Let's talk about mapping meanwhile.

After the mapping process, we need to arrange the obtained files. There is a very nice software to do this. The name of the software is `samtools`.

**Activity 5:** Run the following commands one line at a time.

.. code-block:: bash

   samtools view -S -b -o minion_ch17.bam minion_ch17.sam
   samtools sort minion_ch17.bam > minion_ch17.sorted.bam
   samtools index minion_ch17.sorted.bam

**Activity 6:** Explore mapping results

.. code-block:: bash

   samtools tview -p chr15:30592951 minion_ch17.sorted.bam /share/dennislab/databases/assemblies/GRCh38/hg38.noalt.fa
