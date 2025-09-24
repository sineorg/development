> Some of the items in here are not changes that would be visible to the casual user, and rather would be improvements in the codebase.

-  **Append items to the DOM as XUL elements.**
	Items are currently appended to the DOM as HTML elements to quickly create a neat visual structure, but it would be more beneficial to append them as XUL elements.
	
	Appending them as XUL elements would result in the user being unable to right-click on the elements (making them feel more like native settings in Firefox), and would allow us to quickly style them using XUL's beneficial structure.
-  **Make the `defaultValue` property smart.**
	Currently the `defaultValue` property does not overwrite any pre-existing preferences. This should be changed and the `force` property which was used to do this previously should be removed.
	
	**How should it be implemented?** The `defaultValue` property should be parsed when the mod is installed (not updated) and if it links to a pre-existing preference, it will still overwrite it. However, the `defaultValue` property should be ignored if it links to a pre-existing preference from then on (meaning that normal defaults will be recognized).