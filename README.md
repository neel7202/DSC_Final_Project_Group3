# DSC_Final_Project_Group3

The original dataset used was “100random.xlsx,” an Excel spreadsheet containing 100 randomly generated sentences. If you would like to generate different sentences obtained from the same source, visit https://randomwordgenerator.com/sentence.php and transfer the sentences into a spreadsheet. The blocks of code were run in an Amazon Web Services (AWS) Sagemaker ml.t3.medium instance using a JupyterLab notebook running a python_conda3 kernel.

To recreate or adapt our process, connect to this GitHub repo first. In the TextToSpeechMP3 code, the MP3s were stored in an AWS S3 bucket in the US East (N. Virginia) us-east-1 region. The first line of that file instructs the reader to create their own S3 bucket in which to store their output files. Where the comments in the code say "insert_name = 'XXXX'", replace the "XXXX" to create a new S3 bucket and store the output data in it. The name must be unique, but so that AWS can properly route files to and from each bucket – AWS will notify you if the name is already taken. Once the bucket is created, run all the code in the file to obtain the Amazon Polly-generated mp3 files.

Next, go into the TranscribedCopy code and change the line of code reading "insert_name = 'XXXX'" to the same S3 bucket name used in the TextToSpeechMP3 file. Be sure to use a unique name for the transcribed files if the code is run multiple times so that the the same files are not constantly being overwritten (an easy solution is to put a new number in front of the file name). The "levenshtein" Python library from the "textdistance" package was used to compute the score for each transcription file. 

A more formal walkthrough of the code, reasoning and analysis is included in the “blog” section.
