---
title: Python Docstrings
subtitle: 'A comparison of the various style of documentation commenting'
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2021-04-24'
thumb_image: images/13_thumb.jpg
thumb_image_alt: Library shelves
image: images/13.jpg
image_alt: Library shelves
seo:
  title: The function of design is letting design function
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: The function of design is letting design function
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/13.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: The function of design is letting design function
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/13.jpg
      relativeUrl: true
layout: post
---

This post gives a quick reference to the various Python docstrings.

# Comparison

|                  | Pros                                              | Cons                     |
|------------------|---------------------------------------------------|--------------------------|
| ReStructuredText | Most common format                                | A bit hard to read       |
| Google Style     | Better for short descriptions and documentation   | Not very good for complex documention |
| Numpy Style      | Better for complex descriptions and documentation | Uses more vertical space |

# ReStructured Text

ReStructuredText is a markup language, much like Markdown, that's been used to document code (among other uses).

```python
def func(arg1, arg2):
    """Summary line.

    Extended description of function.

    :param int arg1: Description of arg1.
    :param str arg2: Description of arg2.
    :raise: ValueError if arg1 is equal to arg2
    :return: Description of return value
    :rtype: bool

    :example:

    >>> a=1
    >>> b=2
    >>> func(a,b)
    True
    """

    if arg1 == arg2:
        raise ValueError('arg1 must not be equal to arg2')

    return True
```

# Google Style

```python
def func(arg1, arg2):
    """Summary line.

    Extended description of function.

    Args:
        arg1 (int): Description of arg1
        arg2 (str): Description of arg2

    Returns:
        bool: Description of return value

    Raises:
        AttributeError: The ``Raises`` section is a list of all exceptions
            that are relevant to the interface.
        ValueError: If `arg2` is equal to `arg1`.

    Examples:
        Examples should be written in doctest format, and should illustrate how
        to use the function.

        >>> a=1
        >>> b=2
        >>> func(a,b)
        True

    """
    if arg1 == arg2:
        raise ValueError('arg1 must not be equal to arg2')

    return True
```

# Numpy Style

```python
def func(arg1, arg2):
    """Summary line.

    Extended description of function.

    Parameters
    ----------
    arg1 : int
        Description of arg1
    arg2 : str
        Description of arg2

    Returns
    -------
    bool
        Description of return value

    Raises
    ------
    AttributeError
        The ``Raises`` section is a list of all exceptions
        that are relevant to the interface.
    ValueError
        If `arg2` is equal to `arg1`.

    See Also
    --------
    otherfunc: some other related function

    Examples
    --------
    These are written in doctest format, and should illustrate how to
    use the function.

    >>> a=1
    >>> b=2
    >>> func(a,b)
    True
    """
    if arg1 == arg2:
        raise ValueError('arg1 must not be equal to arg2')

    return True
```

# References

[PEP 257 Docstring Conventions](https://www.python.org/dev/peps/pep-0257/)


