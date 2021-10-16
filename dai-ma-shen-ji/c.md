# c\#

关闭C#软件优化使其在调试时能在任意处下断点。

把

`[assembly:Debuggable(DebuggableAttribute.DebuggingModes.IgnoreSymbolStoreSequencePoints)]`

改成

`[assembly: Debuggable(DebuggableAttribute.DebuggingModes.Default | DebuggableAttribute.DebuggingModes.DisableOptimizations | DebuggableAttribute.DebuggingModes.IgnoreSymbolStoreSequencePoints | DebuggableAttribute.DebuggingModes.EnableEditAndContinue)]`
