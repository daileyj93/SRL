
MainScreen
==========

This file holds functions and procedures that are used for the mainscreen.

 * Ouputs a global variable 'MainScreen' that should be used to call these methods.

.. code-block:: pascal

    srl.Writeln(MainScreen.GetUpText());

MainScreen.GetUpText
~~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    function TRSMainScreen.GetUpText(): String;

Returns the current uptext (Text in top left of the screen).

Example:

.. code-block:: pascal

    srl.Writeln(MainScreen.GetUpText());

MainScreen.IsUpText
~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    function TRSMainScreen.IsUpText(SubStrs: TStringArray; WaitTime: UInt32 = 350): Boolean;

Returns True if any of the strings in 'SubStrs' is in the uptext. Will search up to 'WaitTime'
which by default is 260.

Example:

.. code-block:: pascal

    if (MainScreen.IsUpText(['Attack Chicken', 'ack Chicken'])) then
      Mouse.Click(mouse_Left);

MainScreen.IsUpText; overload
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    function TRSMainScreen.IsUpText(Str: String; WaitTime: UInt32 = 350): Boolean; overload;

Returns True if any of the string 'Str' is in the uptext. Will search up to 'WaitTime'
which by default is 270.

Example:

.. code-block:: pascal

    if (MainScreen.IsUpText('Attack Chicken')) then
      Mouse.Click(mouse_Left);

MainScreen.GetPlayerBox
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    function TRSMainScreen.GetPlayerBox(): TBox;

Returns of a rough Area (TBox) on where your player is.

Example:

.. code-block:: pascal

    Writeln(MainScreen.GetPlayerBox());

MainScreen.FilterPlayerBox
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    procedure TRSMainScreen.FilterPlayerBox(var TPA: TPointArray);

Removes all points in the TPointArray 'TPA' that are in the player box.

Example:

.. code-block:: pascal

    MainScreen.FilterPlayerBox(TPA);

MainScreen.FindHPBars
~~~~~~~~~~~~~~~~~~~~~

.. code-block:: pascal

    function TRSMainScreen.FindHPBars(Area: TBox): THPBarArray;

Returns a THPBarArray of all hitpoint bars found in the area 'Area'.
  * THPBar.Bounds is the bounds of the found hitpoint bar
  * THPBar.Percent is the percent of health in the hitpoint bar.

Example:

.. code-block:: pascal

    Bars := MainScreen.FindHPBars(MainScreen.GetBounds());
