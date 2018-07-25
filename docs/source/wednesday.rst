.. Wednesday Activities

Wednesday activities
====================

Today's schedule:

- 10:00 - 12:00 Linux commands

- 12:00 - 13:00 Lunch break

- 13:00 - 15:00 Quality control

1. Getting into the `matrix` and coding
---------------------------------------

Last monday we learned about computer clusters and we visited the computer cluster in the Genome Center. No we will learn how to perform operations in computer cluster using Linux commands.

1.1 Using the terminal
++++++++++++++++++++++

To control Linux terminal in supercomputers we need to work in a "terminal". Terminal looks like this:

.. image:: https://www.iterm2.com/img/screenshots/split_panes_full.png

MacOS already has a terminal installed, and in Windows we can install MobaXterm:

- Mac: opening Terminal app
- Windows: downloading `MobaXterm`_

.. _`MobaXterm`: http://mobaxterm.mobatek.net/download-home-edition.html

**Activity 0:**  Set up your terminal

1.2 Login to the Cluster
++++++++++++++++++++++++

We can access a super computer remotely from our own computer. To do this, we use a command known as ``ssh``. For this intership, we are going to use a cluster called Comet, located in UCSD.

**Activity 1:** Enter to Comet copy and pasting the following command in the terminal:

.. code-block:: bash

  ssh dcsoto@comet.sdsc.xsede.org

Use the password that we will write on the board!

1.3 Learning Linux commands
+++++++++++++++++++++++++++

What is Linux? To answer this question we need to start with Unix. Unix is an operating system created in the 1960s. An operating system is a group of programs that make the computer work. Linux is an operating system based on Unix. It's free and open-source! That is why is so common in the scientific community. Linux can come in different "flavors", that's what we know as Linux distributions.

Most supercomputers have Linux operating systems. Therefore, to work in a supercomputer we need to learn some Linux commands. These commands will allow us to control remotely the super computer from our personal laptos!

**Activity 2:** Let's learn Linux commands.

The first thing that we will do is to check where is our position in this cluster. Type the following:

.. code-block:: bash

   pwd

What do you see? Every folder is separated by ``/`` symbols. What is "home"?

  ``pwd`` means "print working directory"

Let's look to the files that are in our current folder. We can do this using ``ls`` command. Type:

.. code-block:: bash

   ls

What do you see? The miniconda3 folder contains some software that we are going to use later!

Now we can create personal folders to contain our analysis. First choose a name for your folder. Do You have it? Ok! Now type:

.. code-block:: bash

   mkdir name_of_the_folder

Let's look the folder was succesfully created. Which command can we use?

.. code-block:: bash

   ls

Do you see you folder? Great! Now we can move inside of the super computer to our personal folder. To move inside Linux systems we use the command ``cd``. Type the following:

.. code-block:: bash

   cd name_of_the_folder

Let's check what is our position in the supercomputer. Which command can you use for this?

.. code-block:: bash

   pwd

Great! Now we are going to create a folder to store the data that we are going to use in this internship. Type:

.. code-block:: bash

   mkdir data

Now we can move to the data folder.

.. code-block:: bash

   cd data

Now we are going to start downloading information from the web that we will use later.  We will use sequencing data from two different individuals.

**Activity 3:** Sorting analysis of individuals 1 and 2!

Let's go to the following addresses:

1. URL-1_
2. URL-2_

.. _URL-1: ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG002_NA24385_son/NIST_Illumina_2x250bps/reads/

.. _URL-2: ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG004_NA24143_mother/NIST_Illumina_2x250bps/reads/

**Activity 4:** Download containing genetic information of one of the individuals. To download files in Linux systems, we use the command ``wget`` and the URL to download the file.

1. Copy and paste the following commands:

.. code-block:: bash

   wget ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG002_NA24385_son/NIST_Illumina_2x250bps/reads/D1_S1_L001_R1_001.fastq.gz
   wget ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG002_NA24385_son/NIST_Illumina_2x250bps/reads/D1_S1_L001_R2_001.fastq.gz

2. Copy and paste the following commands:

.. code-block:: bash

   wget ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG004_NA24143_mother/NIST_Illumina_2x250bps/reads/D3_S1_L001_R1_001.fastq.gz
   wget ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG004_NA24143_mother/NIST_Illumina_2x250bps/reads/D3_S1_L001_R2_001.fastq.gz

Great! Today we were able to access the cluster, create folders, and download the data that we need to analyze the genetic information of these individuals.

2. Quality control
------------------

Now, let's give a look at the genomic information that we have. To do this, we will use a program called ``fastqc``. This will generate nice reports that we can visualize in our browser.

1. Copy and paste the following command:

.. code-block:: bash

   fastqc D1_S1_L001_R1_001.fastq.gz
   fastqc D1_S1_L001_R2_001.fastq.gz

2. Copy and paste the following commands:

.. code-block:: bash

   fastqc D3_S1_L001_R1_001.fastq.gz
   fastqc D3_S1_L001_R2_001.fastq.gz

Now, we can look the html files using the browser.
