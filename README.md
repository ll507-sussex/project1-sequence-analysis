Sequencing Read Analysis

Aim
This project uses Python to analyse sequencing reads by comparing them against a reference sequence. To investigate whether treatment impacts the number of mismatches and which positions show the greatest differences between treated and control samples.

Running the Program
The program runs in Google Colab. Open the notebook, make sure the input files are available, and run each code cell in order, starting with the imported libraries and ending with the statistical analysis.

Inputs and Outputs
The program uses sequencing reads, a reference sequence and information about which samples belong to the control or treatment group. It produces summaries showing valid and invalid reads, mismatch percentages, substitution types and mismatch positions. It also identifies the most frequent mismatch positions and compares the two groups using Welch's two-tailed t-test.

Code Design
I organised the program into separate functions so that each part of the analysis has a specific purpose. For example, analyse_reads() checks the reads against the reference sequence, while summarise_samples() collects the results for each sample. This makes the code easier to follow and reduces repetition.

I chose dictionaries to store mismatch counts because they allow each position to be linked directly to its number of mismatches. This also makes it easier to compare positions across different samples.

Another decision was to use .get(position, 0) when retrieving mismatch counts. This means that if a sample has no mismatches at a particular position, it is counted as zero instead of producing an error. Invalid reads are also recorded separately so they are not included when calculating mismatch percentages.

Testing
I checked that all six samples were summarised correctly, with 1,000 valid reads and no invalid reads in each sample. I also checked that positions 97, 98 and 99 were identified as the most frequent mismatch positions. Finally, I tested the statistical comparisons using the mismatch percentages from individual biological samples are tracked separately from valid reads so that mismatch percentages use the number of valid reads as their denominator.
