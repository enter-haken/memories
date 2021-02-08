```
id: 2d24521c-37a0-4335-ad45-de964616d3f6
title: sakura
links:
  - 3060b3e0-aded-493c-a32f-50bd7ef9d824
  - abaa8394-3c19-11ea-b9ab-1fa8afe8f1a2
```

# sakura

A gkt based terminal emulator.

## nord theme

place the following [patch][1] into `/etc/portage/patches/x11-terms/sakura-3.7.1`

```
--- a/src/sakura.c
+++ b/src/sakura.c
@@ -138,6 +138,26 @@ const GdkRGBA solarized_dark_palette[PALETTE_SIZE] = {
 	{0.992157, 0.964706, 0.890196, 1}  // 15 base3
 };
 
+const GdkRGBA nord_palette[PALETTE_SIZE] = {
+    {0.0, 0.0, 0.0234375, 1.0},
+    {0.74609375, 0.37890625, 0.4140625, 1.0},
+    {0.63671875, 0.7421875, 0.546875, 1.0},
+    {0.91796875, 0.79296875, 0.54296875, 1.0},
+    {0.50390625, 0.62890625, 0.75390625, 1.0},
+    {0.703125, 0.5546875, 0.67578125, 1.0},
+    {0.53125, 0.75, 0.8125, 1.0},
+    {0.89453125, 0.91015625, 0.9375, 1.0},
+    {0.296875, 0.3359375, 0.4140625, 1.0},
+    {0.74609375, 0.37890625, 0.4140625, 1.0},
+    {0.63671875, 0.7421875, 0.546875, 1.0},
+    {0.91796875, 0.79296875, 0.54296875, 1.0},
+    {0.50390625, 0.62890625, 0.75390625, 1.0},
+    {0.703125, 0.5546875, 0.67578125, 1.0},
+    {0.55859375, 0.734375, 0.73046875, 1.0},
+    {0.921875, 0.93359375, 0.953125, 1.0},
+};
+
+
 const GdkRGBA xterm_palette[PALETTE_SIZE] = {
     {0,        0,        0,        1},
     {0.803922, 0,        0,        1},
@@ -1703,6 +1723,8 @@ sakura_set_palette(GtkWidget *widget, void *data)
 			sakura.palette=tango_palette;
 		} else if (strcmp(palette, "solarized_dark")==0) {
 			sakura.palette=solarized_dark_palette;
+		} else if (strcmp(palette, "nord")==0) {
+			sakura.palette=nord_palette;
 		} else {
 			/* FIXME: Use a light background */
 			sakura.palette=solarized_dark_palette;
@@ -2048,6 +2070,8 @@ sakura_init()
 		sakura.palette=tango_palette;
 	} else if (strcmp(cfgtmp, "solarized_dark")==0) {
 		sakura.palette=solarized_dark_palette;
+    } else if (strcmp(cfgtmp, "nord")==0) {
+	    sakura.palette=nord_palette;
 	} else {
 		/* FIXME */
 		sakura.palette=solarized_dark_palette;
@@ -2308,7 +2332,7 @@ sakura_init_popup()
 	          *item_blinking_cursor, *item_other_options, 
 	          *item_cursor, *item_cursor_block, *item_cursor_underline, *item_cursor_ibeam,
 	          *item_palette, *item_palette_tango, *item_palette_linux, *item_palette_xterm, *item_palette_rxvt,
-	          *item_palette_solarized_dark, *item_palette_solarized_light, *item_palette_gruvbox,
+	          *item_palette_solarized_dark, *item_palette_solarized_light, *item_palette_nord, *item_palette_gruvbox,
 	          *item_show_close_button, *item_tabs_on_bottom, *item_less_questions,
 	          *item_disable_numbered_tabswitch, *item_use_fading, *item_stop_tab_cycling_at_end_tabs;
 	GtkWidget *options_menu, *other_options_menu, *cursor_menu, *palette_menu;
@@ -2352,6 +2376,7 @@ sakura_init_popup()
 	item_palette_rxvt=gtk_radio_menu_item_new_with_label_from_widget(GTK_RADIO_MENU_ITEM(item_palette_tango), "rxvt");
 	item_palette_solarized_dark=gtk_radio_menu_item_new_with_label_from_widget(GTK_RADIO_MENU_ITEM(item_palette_tango), "Solarized dark");
 	item_palette_solarized_light=gtk_radio_menu_item_new_with_label_from_widget(GTK_RADIO_MENU_ITEM(item_palette_tango), "Solarized light");
+	item_palette_nord=gtk_radio_menu_item_new_with_label_from_widget(GTK_RADIO_MENU_ITEM(item_palette_tango), "Nord");
 
 	/* Show defaults in menu items */
 	gchar *cfgtmp = NULL;
@@ -2438,6 +2463,8 @@ sakura_init_popup()
 		gtk_check_menu_item_set_active(GTK_CHECK_MENU_ITEM(item_palette_rxvt), TRUE);
 	} else if (strcmp(cfgtmp, "solarized_dark")==0) {
 		gtk_check_menu_item_set_active(GTK_CHECK_MENU_ITEM(item_palette_solarized_dark), TRUE);
+	} else if (strcmp(cfgtmp, "nord")==0) {
+		gtk_check_menu_item_set_active(GTK_CHECK_MENU_ITEM(item_palette_nord), TRUE);
 	} else {
 		gtk_check_menu_item_set_active(GTK_CHECK_MENU_ITEM(item_palette_solarized_light), TRUE);
 	}
@@ -2498,6 +2525,7 @@ sakura_init_popup()
 	gtk_menu_shell_append(GTK_MENU_SHELL(palette_menu), item_palette_rxvt);
 	gtk_menu_shell_append(GTK_MENU_SHELL(palette_menu), item_palette_solarized_dark);
 	gtk_menu_shell_append(GTK_MENU_SHELL(palette_menu), item_palette_solarized_light);
+	gtk_menu_shell_append(GTK_MENU_SHELL(palette_menu), item_palette_nord);
 
 	gtk_menu_item_set_submenu(GTK_MENU_ITEM(item_options), options_menu);
 	gtk_menu_item_set_submenu(GTK_MENU_ITEM(item_other_options), other_options_menu);
@@ -2536,6 +2564,7 @@ sakura_init_popup()
 	g_signal_connect(G_OBJECT(item_palette_rxvt), "activate", G_CALLBACK(sakura_set_palette), "rxvt");
 	g_signal_connect(G_OBJECT(item_palette_solarized_dark), "activate", G_CALLBACK(sakura_set_palette), "solarized_dark");
 	g_signal_connect(G_OBJECT(item_palette_solarized_light), "activate", G_CALLBACK(sakura_set_palette), "solarized_light");
+	g_signal_connect(G_OBJECT(item_palette_nord), "activate", G_CALLBACK(sakura_set_palette), "nord");
 
 	g_signal_connect(G_OBJECT(sakura.item_open_mail), "activate", G_CALLBACK(sakura_open_mail), NULL);
 	g_signal_connect(G_OBJECT(sakura.item_open_link), "activate", G_CALLBACK(sakura_open_url), NULL);
```

and reinstall sakura with `emerge -av sakura`.

As you can see, the local patch will be applied.

```
[...]
>>> Emerging (1 of 1) x11-terms/sakura-3.7.1::gentoo
 * sakura-3.7.1.tar.bz2 BLAKE2B SHA512 size ;-) ...                                                                                                                                                                                                                                                                                                                                     [ ok ]
>>> Unpacking source...
>>> Unpacking sakura-3.7.1.tar.bz2 to /var/tmp/portage/x11-terms/sakura-3.7.1/work
>>> Source unpacked in /var/tmp/portage/x11-terms/sakura-3.7.1/work
>>> Preparing source in /var/tmp/portage/x11-terms/sakura-3.7.1/work/sakura-3.7.1 ...
 * Applying sakura-3.7.0-gentoo.patch ...                                                                                                                                                                                                                                                                                                                                               [ ok ]
 * Applying sakura_nord.diff ...                                                                                                                                                                                                                                                                                                                                                        [ ok ]
 * User patches applied.
 * Working in BUILD_DIR: "/var/tmp/portage/x11-terms/sakura-3.7.1/work/sakura-3.7.1_build"
>>> Source prepared.

[...]

* Updating .desktop files database ...                                                                                                                                                                                                                                                                                                                                                 [ ok ]
 * Updating icons cache ...                                                                                                                                                                                                                                                                                                                                                             [ ok ]
>>> Original instance of package unmerged safely.
 * Updating .desktop files database ...                                                                                                                                                                                                                                                                                                                                                 [ ok ]
 * Updating icons cache ...                                                                                                                                                                                                                                                                                                                                                             [ ok ]
>>> x11-terms/sakura-3.7.1 merged.

 * Messages for package x11-terms/sakura-3.7.1:

 * User patches applied.
>>> Auto-cleaning packages...

[...]
```

From now on you can use the `nord` theme.

[1]: https://git.launchpad.net/sakura/commit/?id=6fa244d12be5ea783bf7bab3e40be6c75bf1df5c
