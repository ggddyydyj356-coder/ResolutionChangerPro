package com.example.resolutionchanger

import android.app.Activity
import android.os.Bundle
import android.graphics.Color
import android.view.Gravity
import android.view.ViewGroup
import android.widget.Button
import android.widget.LinearLayout
import android.widget.ScrollView
import android.widget.TextView

class MainActivity : Activity() {

    private val red = Color.rgb(255, 55, 75)
    private val background = Color.rgb(17, 19, 28)
    private val white = Color.WHITE

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        showDashboard()
    }

    private fun showDashboard() {
        val scroll = ScrollView(this)
        val layout = LinearLayout(this).apply {
            orientation = LinearLayout.VERTICAL
            setPadding(24, 30, 24, 30)
            setBackgroundColor(background)
        }

        scroll.addView(layout)

        val title = TextView(this).apply {
            text = "RESOLUTION CHANGER PRO"
            textSize = 25f
            setTextColor(red)
            gravity = Gravity.CENTER
        }

        layout.addView(title)

        val info = TextView(this).apply {
            text = "\nDevice: ${android.os.Build.MODEL}" +
                "\nAndroid: ${android.os.Build.VERSION.RELEASE}" +
                "\n\nResolution and DPI tools\n"
            textSize = 16f
            setTextColor(white)
            gravity = Gravity.CENTER
        }

        layout.addView(info)

        addButton(layout, "Resolution Changer") {
            showMessage("Resolution Changer", "Resolution changes require authorized system access.")
        }

        addButton(layout, "DPI Changer") {
            showMessage("DPI Changer", "DPI changes require authorized system access.")
        }

        addButton(layout, "Crop-to-Resolution") {
            showMessage("Crop Tool", "Crop calculations will be added in a later step.")
        }

        addButton(layout, "Gaming Profiles") {
            showMessage("Gaming Profiles", "Profile management will be added in a later step.")
        }

        addButton(layout, "Permission Manager") {
            showMessage("Permissions", "ADB and Shizuku integration will be added in a later step.")
        }

        addButton(layout, "Restore Default") {
            showMessage("Restore Default", "No display changes have been made by this initial version.")
        }

        setContentView(scroll)
    }

    private fun addButton(
        layout: LinearLayout,
        label: String,
        action: () -> Unit
    ) {
        val button = Button(this).apply {
            text = label
            textSize = 16f
            setTextColor(white)
            setBackgroundColor(Color.rgb(45, 48, 65))
            setOnClickListener { action() }
        }

        layout.addView(
            button,
            LinearLayout.LayoutParams(
                ViewGroup.LayoutParams.MATCH_PARENT,
                ViewGroup.LayoutParams.WRAP_CONTENT
            ).apply {
                setMargins(0, 8, 0, 8)
            }
        )
    }

    private fun showMessage(title: String, message: String) {
        android.app.AlertDialog.Builder(this)
            .setTitle(title)
            .setMessage(message)
            .setPositiveButton("OK", null)
            .show()
    }
}
