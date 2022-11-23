# Swerve Coding Essentials

### Module control

We will need to have a live reading of the current heading of each of our modules. The best way to get this value of a module's current heading is by using an absolute encoder, as it will always be accurate no matter where the module was when the robot initialized.

{% hint style="info" %}
Some examples of Absolute Encoders:

MA3: [https://www.andymark.com/products/ma3-absolute-encoder-with-cable](https://www.andymark.com/products/ma3-absolute-encoder-with-cable)

Lamprey: [https://www.andymark.com/products/lamprey-absolute-encoder](https://www.andymark.com/products/lamprey-absolute-encoder)

Redux: [https://axon-robotics.com/products/redux-encoder](https://axon-robotics.com/products/redux-encoder)

AS5600: [https://www.amazon.com/Magnetic-Encoder-Induction-Measurement-Precision/dp/B097QNG1CN](https://www.amazon.com/Magnetic-Encoder-Induction-Measurement-Precision/dp/B097QNG1CN)
{% endhint %}

<pre class="language-java" data-line-numbers><code class="lang-java"><strong>//Define the analogInput from hardwaremap
</strong><strong>double voltRange = 3.3;
</strong><strong>AnalogInput analogEncoder = hardwareMap.get(AnalogInput.class, "anAnalogEncoder");
</strong><strong>
</strong><strong>//read the voltage from the analog port
</strong><strong>//convert the voltage to a range between 0 and 1
</strong><strong>//multiply by 360 to get this value into degrees
</strong>double modulePosition = analogInput.getVoltage() / voltRange * 360;</code></pre>

### PID Control

PID is the system that we will actually be using to move the swerve module's to the desired position. There are resources for learning PID control, and therefore the focus here will be specifically on how to use PID for swerve.&#x20;

{% hint style="info" %}
or PID control, see:&#x20;

[https://www.ctrlaltftc.com/](https://www.ctrlaltftc.com/)

[https://gm0.org/en/latest/docs/software/concepts/control-loops.html](https://gm0.org/en/latest/docs/software/concepts/control-loops.html)
{% endhint %}

The basic PID controller will be all that is needed to turn the modules, with just a few edits.
