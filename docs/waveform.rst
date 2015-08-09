Analyzing audio
=========
 
.. codeblock: bash

    ffmpeg -i in.wav -ac 1 -filter:a aresample=8000 -map 0:a -c:a pcm_s16le -f data - > binaryfile

.. codeblock: python

    import numpy as np
    waveform_data = np.fromfile('binaryfile', dtype = 'int16')
