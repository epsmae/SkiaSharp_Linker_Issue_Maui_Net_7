# Sample Repo for SkiaSharp Linker Issue with Startup Tracing

1. dotnet new maui
2. Install lates SkiaSharp.Views.Maui.Controls and SkiaSharp.Views.Maui.Controls.Compatibility
3. dotnet workload restore
4. dotnet restore
5. dotnet build
6. dotnet publish -f:net6.0-android -c:Release


## Issue

```
ILLink : error IL1011: Failed to write 'obj\Release\net7.0-android\android-arm\linked\SkiaSharp.Views.Android.dll'. [D:
\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
  Fatal error in IL Linker
  Unhandled exception. Mono.Linker.LinkerFatalErrorException: ILLink: error IL1011: Failed to write 'obj\Release\net7.0
  -android\android-arm\linked\SkiaSharp.Views.Android.dll'.
   ---> System.ArgumentException: Member 'System.Int32 SKCanvasView_ignorePixelScaling' is declared in another module a
  nd needs to be imported
     at Mono.Cecil.MetadataBuilder.LookupToken(IMetadataTokenProvider provider)
     at Mono.Cecil.Cil.CodeWriter.WriteOperand(Instruction instruction)
     at Mono.Cecil.Cil.CodeWriter.WriteInstructions()
     at Mono.Cecil.Cil.CodeWriter.WriteResolvedMethodBody(MethodDefinition method)
     at Mono.Cecil.Cil.CodeWriter.WriteMethodBody(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethod(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethods(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddType(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddTypes()
     at Mono.Cecil.MetadataBuilder.BuildTypes()
     at Mono.Cecil.MetadataBuilder.BuildModule()
     at Mono.Cecil.MetadataBuilder.BuildMetadata()
     at Mono.Cecil.ModuleWriter.<>c.<BuildMetadata>b__2_0(MetadataBuilder builder, MetadataReader _)
     at Mono.Cecil.ModuleDefinition.Read[TItem,TRet](TItem item, Func`3 read)
     at Mono.Cecil.ModuleWriter.BuildMetadata(ModuleDefinition module, MetadataBuilder metadata)
     at Mono.Cecil.ModuleWriter.Write(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleWriter.WriteModule(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Cecil.AssemblyDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     --- End of inner exception stack trace ---
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory)
     at Mono.Linker.Steps.OutputStep.OutputAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.OutputStep.ProcessAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.BaseStep.Process(LinkContext context)
     at Mono.Linker.Pipeline.ProcessStep(LinkContext context, IStep step)
     at Mono.Linker.Pipeline.Process(LinkContext context)
     at Mono.Linker.Driver.Run(ILogger customLogger)
     at Mono.Linker.Driver.Main(String[] args)
ILLink : error IL1011: Failed to write 'obj\Release\net7.0-android\android-arm64\linked\SkiaSharp.Views.Android.dll'. [
D:\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
  Fatal error in IL Linker
  Unhandled exception. Mono.Linker.LinkerFatalErrorException: ILLink: error IL1011: Failed to write 'obj\Release\net7.0
  -android\android-arm64\linked\SkiaSharp.Views.Android.dll'.
   ---> System.ArgumentException: Member 'System.Int32 SKCanvasView_ignorePixelScaling' is declared in another module a
  nd needs to be imported
     at Mono.Cecil.MetadataBuilder.LookupToken(IMetadataTokenProvider provider)
     at Mono.Cecil.Cil.CodeWriter.WriteOperand(Instruction instruction)
     at Mono.Cecil.Cil.CodeWriter.WriteInstructions()
     at Mono.Cecil.Cil.CodeWriter.WriteResolvedMethodBody(MethodDefinition method)
     at Mono.Cecil.Cil.CodeWriter.WriteMethodBody(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethod(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethods(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddType(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddTypes()
     at Mono.Cecil.MetadataBuilder.BuildTypes()
     at Mono.Cecil.MetadataBuilder.BuildModule()
     at Mono.Cecil.MetadataBuilder.BuildMetadata()
     at Mono.Cecil.ModuleWriter.<>c.<BuildMetadata>b__2_0(MetadataBuilder builder, MetadataReader _)
     at Mono.Cecil.ModuleDefinition.Read[TItem,TRet](TItem item, Func`3 read)
     at Mono.Cecil.ModuleWriter.BuildMetadata(ModuleDefinition module, MetadataBuilder metadata)
     at Mono.Cecil.ModuleWriter.Write(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleWriter.WriteModule(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Cecil.AssemblyDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     --- End of inner exception stack trace ---
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory)
     at Mono.Linker.Steps.OutputStep.OutputAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.OutputStep.ProcessAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.BaseStep.Process(LinkContext context)
     at Mono.Linker.Pipeline.ProcessStep(LinkContext context, IStep step)
     at Mono.Linker.Pipeline.Process(LinkContext context)
     at Mono.Linker.Driver.Run(ILogger customLogger)
     at Mono.Linker.Driver.Main(String[] args)
ILLink : error IL1011: Failed to write 'obj\Release\net7.0-android\android-x86\linked\SkiaSharp.Views.Android.dll'. [D:
\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
  Fatal error in IL Linker
  Unhandled exception. Mono.Linker.LinkerFatalErrorException: ILLink: error IL1011: Failed to write 'obj\Release\net7.0
  -android\android-x86\linked\SkiaSharp.Views.Android.dll'.
   ---> System.ArgumentException: Member 'System.Int32 SKCanvasView_ignorePixelScaling' is declared in another module a
  nd needs to be imported
     at Mono.Cecil.MetadataBuilder.LookupToken(IMetadataTokenProvider provider)
     at Mono.Cecil.Cil.CodeWriter.WriteOperand(Instruction instruction)
     at Mono.Cecil.Cil.CodeWriter.WriteInstructions()
     at Mono.Cecil.Cil.CodeWriter.WriteResolvedMethodBody(MethodDefinition method)
     at Mono.Cecil.Cil.CodeWriter.WriteMethodBody(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethod(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethods(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddType(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddTypes()
     at Mono.Cecil.MetadataBuilder.BuildTypes()
     at Mono.Cecil.MetadataBuilder.BuildModule()
     at Mono.Cecil.MetadataBuilder.BuildMetadata()
     at Mono.Cecil.ModuleWriter.<>c.<BuildMetadata>b__2_0(MetadataBuilder builder, MetadataReader _)
     at Mono.Cecil.ModuleDefinition.Read[TItem,TRet](TItem item, Func`3 read)
     at Mono.Cecil.ModuleWriter.BuildMetadata(ModuleDefinition module, MetadataBuilder metadata)
     at Mono.Cecil.ModuleWriter.Write(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleWriter.WriteModule(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Cecil.AssemblyDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     --- End of inner exception stack trace ---
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory)
     at Mono.Linker.Steps.OutputStep.OutputAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.OutputStep.ProcessAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.BaseStep.Process(LinkContext context)
     at Mono.Linker.Pipeline.ProcessStep(LinkContext context, IStep step)
     at Mono.Linker.Pipeline.Process(LinkContext context)
     at Mono.Linker.Driver.Run(ILogger customLogger)
     at Mono.Linker.Driver.Main(String[] args)
C:\Program Files\dotnet\sdk\7.0.100\Sdks\Microsoft.NET.ILLink.Tasks\build\Microsoft.NET.ILLink.targets(86,5): error NET
SDK1144: Optimizing assemblies for size failed. Optimization can be disabled by setting the PublishTrimmed property to
false. [D:\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
ILLink : error IL1011: Failed to write 'obj\Release\net7.0-android\android-x64\linked\SkiaSharp.Views.Android.dll'. [D:
\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
  Fatal error in IL Linker
  Unhandled exception. Mono.Linker.LinkerFatalErrorException: ILLink: error IL1011: Failed to write 'obj\Release\net7.0
  -android\android-x64\linked\SkiaSharp.Views.Android.dll'.
   ---> System.ArgumentException: Member 'System.Int32 SKCanvasView_ignorePixelScaling' is declared in another module a
  nd needs to be imported
     at Mono.Cecil.MetadataBuilder.LookupToken(IMetadataTokenProvider provider)
     at Mono.Cecil.Cil.CodeWriter.WriteOperand(Instruction instruction)
     at Mono.Cecil.Cil.CodeWriter.WriteInstructions()
     at Mono.Cecil.Cil.CodeWriter.WriteResolvedMethodBody(MethodDefinition method)
     at Mono.Cecil.Cil.CodeWriter.WriteMethodBody(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethod(MethodDefinition method)
     at Mono.Cecil.MetadataBuilder.AddMethods(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddType(TypeDefinition type)
     at Mono.Cecil.MetadataBuilder.AddTypes()
     at Mono.Cecil.MetadataBuilder.BuildTypes()
     at Mono.Cecil.MetadataBuilder.BuildModule()
     at Mono.Cecil.MetadataBuilder.BuildMetadata()
     at Mono.Cecil.ModuleWriter.<>c.<BuildMetadata>b__2_0(MetadataBuilder builder, MetadataReader _)
     at Mono.Cecil.ModuleDefinition.Read[TItem,TRet](TItem item, Func`3 read)
     at Mono.Cecil.ModuleWriter.BuildMetadata(ModuleDefinition module, MetadataBuilder metadata)
     at Mono.Cecil.ModuleWriter.Write(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleWriter.WriteModule(ModuleDefinition module, Disposable`1 stream, WriterParameters parameters)
     at Mono.Cecil.ModuleDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Cecil.AssemblyDefinition.Write(String fileName, WriterParameters parameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     --- End of inner exception stack trace ---
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory, WriterParameters writ
  erParameters)
     at Mono.Linker.Steps.OutputStep.WriteAssembly(AssemblyDefinition assembly, String directory)
     at Mono.Linker.Steps.OutputStep.OutputAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.OutputStep.ProcessAssembly(AssemblyDefinition assembly)
     at Mono.Linker.Steps.BaseStep.Process(LinkContext context)
     at Mono.Linker.Pipeline.ProcessStep(LinkContext context, IStep step)
     at Mono.Linker.Pipeline.Process(LinkContext context)
     at Mono.Linker.Driver.Run(ILogger customLogger)
     at Mono.Linker.Driver.Main(String[] args)
C:\Program Files\dotnet\sdk\7.0.100\Sdks\Microsoft.NET.ILLink.Tasks\build\Microsoft.NET.ILLink.targets(86,5): error NET
SDK1144: Optimizing assemblies for size failed. Optimization can be disabled by setting the PublishTrimmed property to
false. [D:\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
C:\Program Files\dotnet\sdk\7.0.100\Sdks\Microsoft.NET.ILLink.Tasks\build\Microsoft.NET.ILLink.targets(86,5): error NET
SDK1144: Optimizing assemblies for size failed. Optimization can be disabled by setting the PublishTrimmed property to
false. [D:\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]
C:\Program Files\dotnet\sdk\7.0.100\Sdks\Microsoft.NET.ILLink.Tasks\build\Microsoft.NET.ILLink.targets(86,5): error NET
SDK1144: Optimizing assemblies for size failed. Optimization can be disabled by setting the PublishTrimmed property to
false. [D:\EPS\MauiBugs\SkiaSharpSample\SkiaSharpSample.csproj::TargetFramework=net7.0-android]

```