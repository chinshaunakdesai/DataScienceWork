
Script Name

NGrams_TransactionParser_v2.0.ipynb


REQUIREMENTS
The only external library used was tqdm.
It should work on any OS with Python 3.X.

SCRIP CONFIGURATION

In the script you have the following snipped:

# SETTINGS
INPUT_FILE = 'retail_25k.dat'  # Input file local name or path
N = 3                          # The length of combination performed
SIGMA = 4                      # The filter of the combined data
OUTPUT_FILE = 'output.txt'     # Name of the desired output file


Although each variable is commented with its function in the code, here is a more detailed description.

INPUT_FILE: The name (if the file is in the same directory of the script) or complete path to the file to be analysed. 
The input file should consists of a multiple lines of integers separated by spaces, which each line represents a transaction
and each integer an item. Additionally, the numbers should be in increasing order. 
Example of input file: '1 2 3 6 16 25 2005'.

N: The Number of combinations searched for each transaction in the input data.
Example: Assume input data equals to '1 2 3 4' and N=3, then the possible combinations for this transaction are (1,2,3), 
(1,2,4),(1,3,4), (2,3,4).

SIGMA: The threshold used to filter the number of combinations that appears equals or above this value.
Example:  Assume N=2, SIGMA=2 and input data shown bellow
INPUT_DATA: '1 2 3 4 5'
                        '1 3 5'
Filtered Combinations:
(1,3): 2
(1,5): 2

OUTPUT_FILE: Name of the desired output file( if you want the file to be saved in the same directory of the script), or the
complete path to file. The file is in the format: <item set size (N)>, <co-occurrence frequency>, <item 1 id >, <item 2 id>,
 …. <item N id>.

Example:  Assume N=2, SIGMA=2 and input data shown bellow.
INPUT_DATA:     '1 2 3 4 5'
                            '1 3 5'
OUTPUT_DATA: '2 2 1 3'
                            '2 2 1 5'
