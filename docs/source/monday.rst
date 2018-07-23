.. Monday Activities

Monday Activities
=================

Today's schedule:

- 9:00 - 10:30 Markdown

- 10:30 - 10:45 Break

- 10:45 - 12:00 Linux

- 12:00 - 13:00 Lunch break

- 13:00 - 15:00 Visiting the cluster

1. Introduction
---------------

Computers are getting more and more important every year in most fields. Biology and genetics is not the exception. Nowadays, almost every experiment involves some kind of computational analysis. You have already interacted with some online tools (UCSC genome browser, for example), but now we are going to work from the "command line" and code!

2. Digital lab notebook
-----------------------

The first and most important part is to take notes about all the analysis that you are doing! Same as when you were working in the laboratory, everything that you do in the computer should be written down.

To do this, we are going to learn a language called “Markdown”. This language allows you to write a plain text file, and the it takes the trouble to render it beautifully. Why is this better than a Microsoft Word document or a simple txt file? Because it allows you to write your code and format it easily!

**Activity 1:** To start, let's complete this online tutorial: `Markdown Tutorial`_

.. _`Markdown Tutorial`: https://www.markdowntutorial.com/
**Activity 2:** Now that you know how to write using Markdown, create your own lab notebook using Hackmd_

.. _Hackmd: https://hackmd.io/

**Activity 3:** Start your labnotebook file. Include titles, subtitles, and document everything that your learned about Markdown in your own words.

3. Getting into the `matrix` and coding
---------------------------------------

3.1 Computer clusters
+++++++++++++++++++++

To analyze the big amount of sequencing data that we can generate with sequencing technologies, bioinformaticians need supercomputers. Most supercomputers have Linux systems.

Some questions:
  - Have you heard of Linux before?
  - Why do you think most supercomputers use Linux?

"Supercomputers" actually are multiple computers linked together. This configurations is known as "computer cluster". Here is a picture of a very powerful computer cluster called IBM Sequoia:

.. image:: http://www.digitaltrends.com/wp-content/uploads/2012/06/IBM-Sequoia.jpg

Here int he Genome Center, we also have our own computer cluster that we will visit at 1pm!

3.2 Using the terminal
++++++++++++++++++++++

To control Linux terminal in supercomputers we need to work in a "terminal". Terminal looks like this:

.. image:: https://www.iterm2.com/img/screenshots/split_panes_full.png

MacOS already has a terminal installed, and in Windows we can install MobaXterm:

- Mac: opening Terminal app
- Windows: downloading MobaXterm_

.. _MobaXterm:: http://mobaxterm.mobatek.net/download-home-edition.html

**Activity 4:**  Set up your terminal

3.3 Login to the Cluster
++++++++++++++++++++++++

We can access a super computer remotely from our own computer. To do this, we use a command known as ``ssh``. For this intership, we are going to use a cluster called Comet, located in UCSD.

**Activity 5:** Enter to Comet copy and pasting the following command in the terminal:

.. code-block:: bash

  ssh dcsoto@comet.sdsc.xsede.org

Use the password that we will write on the board!

3.4 Learning Linux commands
+++++++++++++++++++++++++++

What is Linux? To answer this question we need to start with Unix. Unix is an operating system created in the 1960s. An operating system is a group of programs that make the computer work. Linux is an operating system based on Unix. It's free and open-source! That is why is so common in the scientific community. Linux can come in different "flavors", that's what we know as Linux distributions.

Most supercomputers have Linux operating systems. Therefore, to work in a supercomputer we need to learn some Linux commands. These commands will allow us to control remotely the super computer from our personal laptos!

**Activity 6:** Let's learn Linux commands.

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

Let's go to the following addresses:

1. URL-1_
2. URL-2_


.. _URL-1

   ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG002_NA24385_son/NIST_Illumina_2x250bps/reads/

.. _URL-2

   ftp://ftp-trace.ncbi.nlm.nih.gov/giab/ftp/data/AshkenazimTrio/HG004_NA24143_mother/NIST_Illumina_2x250bps/reads/

We will download

**Activity 8:** Download files containing genetic information of one of the individuals. To download files in Linux systems, we use the command ``wget``. Right click over the first file, the use "copy link address". Then use:

.. code-block:: bash

   wget paste_url

Great! Today we were able to access the cluster, create folders, and download the data that we need to analyze the genetic information of these individuals.

4. Visit to our computer cluster
++++++++++++++++++++++++++++++++

**Activity 8:** Register everything that you learned about computer clusters in your Hackmd document using Markdown language.
