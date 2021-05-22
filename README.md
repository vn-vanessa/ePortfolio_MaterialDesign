# Material Design - e-Portfolio
Material Design ist ein Designsystem, das 2014 von Google vorgestellt wurde.
Das System kann zur Gestaltung von Android und iOS Apps und Websistes verwendet werden.

Auf [material.io](https://material.io) ist die Doku zu finden, in der die Design Guidelines und die Material Components nachgelesen werden können.
Die Slides zum e-Portfolio sind hier verlinkt.

In der Demo wird zum erstellen eines Material Themes der MaterialThemeBuilder verwendet, der von
[Google](https://github.com/material-components) bereitgestellt wird.
Außerdem werden folgende Tools verwendet:
- [Color Tool](https://material.io/resources/color/#!/?view.left=0&view.right=0)
- [alternativ Color Palette Generator](https://material.io/design/color/the-color-system.html#tools-for-picking-colors)
- [Shape Tool](https://material.io/design/shape/about-shape.html#shape-customization-tool)
- [Type Tool](https://material.io/design/typography/the-type-system.html?utm_source=Medium&utm_campaign=TE-post#type-scale)

Um während der Demo mitzumachen, braucht ihr Android Studio und einen Emulator. Anschließend könnt ihr dieses repository clonen.
Am besten vorher einmal in der IDE testen, ob der MaterialThemeBuilder im Emulator funktioniert.

Die Demo bezieht sich auf Matherial Theming für Android, der MaterialThemeBuilder wird aber auch fürs Web auf
[Glitch](https://glitch.com/~material-theme-builder) bereitgestellt.
Dort könnt ihr in dem Projekt ähnlich zu der Demo die Werte (Farben, Formen,...) anpassen und so ein Material Theme für eure Website erstellen.

## Ein Material Theme erstellen/anpassen
Mit dem MaterialThemeBuilder kann man ein eigenes Materiel Theme erstellen bzw. anpassen.

Themes bestehen hauptsächlich aus Farbe, Typographie und Form.
Diese kann man im MaterialThemeBuilder in den xml-Files (App resources) anpassen und direkt in der App sehen, wie das Theme in der App aussieht.

Apps, die mit Material Design erstellt werden, erben die Material Standard-Theme (türkis-violettes Farb-Theme).

Um dieses Theme an ein eigenes Design anzupassen, müssen die Werte in den Dateien shape.xml, color.xml und type.xml angepasst werden.

### color.xml
Um das Farbschema zu ändern, kann man die HEX-Werte in der color.xml ersetzen/ändern.
Da Apps zusätzlich oft einen Dark-Mode haben, kann man im MaterialThemeBuilder mithilfe des Toggles auf der Instructions-Page auch den Dark-Mode anschauen.

Nützliche Tools:
- [Color Tool](https://material.io/resources/color/#!/?view.left=0&view.right=0)
- [alternativ Color Palette Generator](https://material.io/design/color/the-color-system.html#tools-for-picking-colors)

### shape.xml
Um das Form-Schema zu ändern, kann man den ShapeApperance-Style in der shape.xml Datei verändern.
Man unterscheidet bei den Ecken der Komponenten zwischen 'rounded' oder cut'.
Diese Form kann mit cornerFamily auf alle 4 Ecken einer Komponente angewendet werden, oder mit cornerFamilyBottomLeft etc nur für jeweils eine Ecke.
cornerSize legt fest, wie groß die Rundung/Abschrägung ist.

Außerdem werden die Komponenten in drei [Gruppen](https://material.io/design/shape/applying-shape-to-ui.html#shape-scheme) (small, medium und large) eingeteilt.
Jede der drei Gruppen kann durch Anpassen des shapeAppearanceSmallComponent, shapeAppearanceMediumComponent oder shapeAppearanceLargeComponent
Styles angepasst werden.

Mit shapeAppearanceOverlay können einzelne Komponenten angepasst werden (shapeAppearance Styles werden überschrieben).

Nützliche Tools:
- [Shape Tool](https://material.io/design/shape/about-shape.html#shape-customization-tool)
- [Doku](https://material.io/develop/android/theming/shape)

### type.xml
Um die Typogarphie des Themes anzupassen, kann man Schriftarten von [Google Fonts](https://fonts.google.com/) kombiniert mit dem
[Type scale generator](https://material.io/design/typography/the-type-system.html?utm_source=Medium&utm_campaign=TE-post#type-scale) verwenden.
Der Type scale genarator generiert anhand der ausgweählten Schriftart direkt den passenden Code, der in die type.xml übernommen werden kann.

Alternativ können auch die fontFamily und die textSize manuell in der type.xml Datei angepasst bzw. verändert werden.
Auch die Textfarbe (textColor), der Zeichenabstand (letterSpacing) etc. können hier global festgelegt werden.

Wenn man keine Schriftart von Google Fonts verwenden möchte, kann man seinem Projekt auch eine andere Schriftart (im ttf-Format)
hinzufügen und diese im type.xml verwenden. ([Tutorial](https://developer.android.com/guide/topics/ui/look-and-feel/fonts-in-xml))

Nützliche Tools:
- [Google Fonts](https://fonts.google.com/)
- [Type scale generator](https://material.io/design/typography/the-type-system.html?utm_source=Medium&utm_campaign=TE-post#type-scale)
- [Learn how to add fonts in Android Studio](https://developer.android.com/guide/topics/ui/look-and-feel/downloadable-fonts)

## Die letzten Schritte...
Wenn das Theme fertig ist, kann man die Ressourcen (xml-Files die wir verändert haben, also color.xml, type.xml,... und auch die beiden themes.xml and night/themes.xml)
in das eigentliche Projekt verschieben und das Theme so im eigenen Projekt verwenden.
Dafür muss nur noch der Name des Themes in der AndroidManifest.xml angepasst werden (android:theme="@style/Theme.MyApp").
