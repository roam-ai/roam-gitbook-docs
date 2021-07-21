# Troubleshooting

## Proguard rules

If you enables code shrinking, obfuscation, and optimization in your project's release build type minifyEnabled true, add the below line in your [proguard-rules.pro](http://proguard-rules.pro/).

```text
-keep class com.amazonaws.**
```

