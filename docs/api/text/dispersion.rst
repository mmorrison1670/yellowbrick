.. -*- mode: rst -*-

Dispersion Plot
===============

A word's importance can be weighed by its dispersion in a corpus.  Lexical dispersion is a measure of a word's homogeneity across the parts of a corpus.  This plot notes the occurrences of a word and how many words from the beginning of the corpus it appears.

=================   ==============================
Visualizer           `DispersionPlot <https://www.scikit-yb.org/en/latest/api/text/dispersion.html#yellowbrick.text.dispersion.DispersionPlot>`_
Quick Method         `dispersion() <https://www.scikit-yb.org/en/latest/api/text/dispersion.html#yellowbrick.text.dispersion.dispersion>`_
Models               Text Modeling
Workflow             Feature Engineering
=================   ==============================

.. plot::
    :context: close-figs
    :alt: Dispersion Plot

    from yellowbrick.text import DispersionPlot
    from yellowbrick.datasets import load_hobbies

    # Load the text data
    corpus = load_hobbies()

    # Create a list of words from the corpus text
    text = [doc.split() for doc in corpus.data]

    # Choose words whose occurence in the text will be plotted
    target_words = ['Game', 'player', 'score', 'oil', 'Man']

    # Create the visualizer and draw the plot
    visualizer = DispersionPlot(target_words)
    visualizer.fit(text)
    visualizer.show()

Quick Method
-------------------------
The same functionality above can be achieved with the associated quick method `dispersion`. This method will build the Dispersion Plot object with the associated arguments, fit it, then (optionally) immediately show the visualization.

.. plot::
    :context: close-figs
    :alt: Quick Method Dispersion Plot

    from yellowbrick.text import DispersionPlot, dispersion
    from yellowbrick.datasets import load_hobbies

    # Load the text data
    corpus = load_hobbies()

    # Create a list of words from the corpus text
    text = [doc.split() for doc in corpus.data]

    # Choose words whose occurence in the text will be plotted
    target_words = ['features', 'mobile', 'cooperative', 'competitive', 'combat', 'online']

    # Create the visualizer and draw the plot
    dispersion(target_words, text)

API Reference
-------------

.. automodule:: yellowbrick.text.dispersion
    :members: DispersionPlot, dispersion
    :undoc-members:
    :show-inheritance:
