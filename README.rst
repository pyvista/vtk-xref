VTK XRef
========

``vtk-xref`` is a Sphinx extension for linking directly to
`VTK's documentation <https://vtk.org/doc/nightly/html/index.html>`_
using the ``:vtk:`` reference role.

Installation
------------

#.  Add ``vtk-xref`` as a project dependency or install it with:

    .. code-block:: bash

        pip install vtk-xref


#.  Add ``vtk_xref`` as an extension in your ``conf.py`` file
    used by Sphinx:

.. code-block:: python

    extensions = [
        ...,
        'vtk_xref',
    ]

Usage
-----

- Add links to VTK class documentation with the ``:vtk:`` role. For
  example, write ``:vtk:`vtkImageData``` in docstrings to link directly
  to the ``vtkImageData`` documentation. This will render as
  `vtkImageData <https://vtk.org/doc/nightly/html/classvtkImageData.html>`_.

- Link directly to class members such as methods or enums. For example,
  write ``:vtk:`vtkImageData.GetDimensions``` to link directly to the
  ``GetDimensions`` method. This will render as
  `vtkImageData.GetDimensions <https://vtk.org/doc/nightly/html/classvtkImageData.html#a3cbcab15f8744efeb5300e21dcfbe9af>`_.

- Use ``~`` to shorten the title for the link and only show the class member
  after the period. For example, ``:vtk:`~vtkImageData.GetDimensions```
  will render as
  `GetDimensions <https://vtk.org/doc/nightly/html/classvtkImageData.html#a3cbcab15f8744efeb5300e21dcfbe9af>`_.

- Provide a custom title for the reference. For example,
  ``:vtk:`Get Image Dimensions <vtkImageData.GetDimensions>```
  will render as
  `Get Image Dimensions <https://vtk.org/doc/nightly/html/classvtkImageData.html#a3cbcab15f8744efeb5300e21dcfbe9af>`_

Notes
-----

- The URLs linking to the VTK documentation are checked to ensure they are valid
  references. A warning is emitted if the reference is invalid, but the role
  will still try to point to a valid URL where possible. It is recommended to
  set ``nitpicky=True`` in ``conf.py`` when using this extension to ensure all
  links are valid and correct.

- The role does not currently support linking to nested members. For example,
  linking to an enum member with ``:vtk:`vtkCommand.EventIds``` works,
  but linking to a specific enum value with ``:vtk:`vtkCommand.EventIds.PickEvent```
  does not.
