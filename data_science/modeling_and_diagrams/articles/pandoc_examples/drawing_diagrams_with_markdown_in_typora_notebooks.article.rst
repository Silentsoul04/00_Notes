.. _header-n3:

Draw Diagrams With Markdown
===========================

Typora supports some Markdown extension for diagrams, you could enable
this feature from preference panel.

When exporting as HTML, PDF, epub, docx, those rendered diagrams will
also be included, but diagrams features are not supported when exporting
markdown into other file formats in current version. Besides, you should
also notice that diagrams is not supported by standard Markdown,
CommonMark or GFM. Therefore, we still recommend you to insert an image
of these diagrams instead of write them in Markdown directly.

--------------

.. _header-n9:

Sequence
--------

It is powered by js-sequence, which would turn following code block into
rendered diagrams:

.. code:: sequence

    Alice->Bob: Hello Bob, how are you?
    Note right of Bob: Bob thinks
    Bob-->Alice: I am good thanks!

Please refer here for syntax explanation.

--------------

.. _header-n17:

Flowchart
---------

It is powered by flowchart.js, which would turn following code block
into rendered diagrams:

.. code:: flow

    st=>start: Start
    op=>operation: Your Operation
    cond=>condition: Yes or No?
    e=>end

    st->op->cond
    cond(yes)->e
    cond(no)->op

--------------

.. _header-n23:

Mermaid
-------

Typora also has integration with mermaid, which supports sequence,
flowchart and Gantt.

.. _header-n26:

Sequence
--------

see this doc

.. code:: mermaid

    %% Example of sequence diagram
      sequenceDiagram
        Alice->>Bob: Hello Bob, how are you?
        alt is sick
        Bob->>Alice: Not so good :(
        else is well
        Bob->>Alice: Feeling fresh like a daisy
        end
        opt Extra response
        Bob->>Alice: Thanks for asking
        end

.. _header-n31:

Flowchart
---------

see this doc

.. code:: mermaid

    graph LR
    A[Hard edge] -->B(Round edge)
        B --> C{Decision}
        C -->|One| D[Result one]
        C -->|Two| E[Result two]

.. _header-n37:

Gantt
-----

see this doc

.. code:: mermaid

    %% Example with slection of syntaxes
            gantt
            dateFormat  YYYY-MM-DD
            title Adding GANTT diagram functionality to mermaid

            section A section
            Completed task            :done,    des1, 2014-01-06,2014-01-08
            Active task               :active,  des2, 2014-01-09, 3d
            Future task               :         des3, after des2, 5d
            Future task2               :         des4, after des3, 5d

            section Critical tasks
            Completed task in the critical line :crit, done, 2014-01-06,24h
            Implement parser and jison          :crit, done, after des1, 2d
            Create tests for parser             :crit, active, 3d
            Future task in critical line        :crit, 5d
            Create tests for renderer           :2d
            Add to mermaid                      :1d

            section Documentation
            Describe gantt syntax               :active, a1, after des1, 3d
            Add gantt diagram to demo page      :after a1  , 20h
            Add another diagram to demo page    :doc1, after a1  , 48h

            section Last section
            Describe gantt syntax               :after doc1, 3d
            Add gantt diagram to demo page      : 20h
            Add another diagram to demo page    : 48h
