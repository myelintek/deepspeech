# deepspeech
## Entry.ipynb - notebook file for building DeepSpeech
## Demo.ipynb - notebook file that allows to show inference processes (Chinese and English languages)
## Train.ipynb - notebook file that allows to start a training process (Chinese language). Training data is Common Voice dataset (Chinese language, Taiwanese) https://commonvoice.mozilla.org/zh-TW/datasets
### Later English version will be added
### Generating alphabet.txt file for Chinese dataset is the most challenging part, so we prepared it in advance
### Put alphabet.txt file to DeepSpeech/data/ folder
### To avoid the training process problem, local/lib/python3.6/dist-packages/ds_ctcdecoder/__init__.py file should be changed as follows:
def Decode(self, input):
        '''Decode a sequence of labels into a string.'''
        res = super(UTF8Alphabet, self).Decode(input)
        return res.decode('utf-8', 'ignore')
