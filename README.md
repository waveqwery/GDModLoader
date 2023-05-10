# GDModLoader
Mod that allows you to load dynamic libraries in GD.
Download [Apk tool](https://ibotpeaches.github.io/Apktool/) and use it to decompile Geometry Dash.
Edit the main class by adding the method below.
API level 28+.

```
# virtual methods
.method public initMods()V
    .locals 2

    .line 17
    const-string v0, "GDModLoader"

    invoke-static {v0}, Lru/krazy/gdml/GeometryDashLoaderLibs;->CreateDirectory(Ljava/lang/String;)V

    .line 18
    new-instance v0, Ljava/lang/StringBuilder;

    invoke-direct {v0}, Ljava/lang/StringBuilder;-><init>()V

    const-string v1, "/data/data/"

    invoke-virtual {v0, v1}, Ljava/lang/StringBuilder;->append(Ljava/lang/String;)Ljava/lang/StringBuilder;

    move-result-object v0

    invoke-virtual {p0}, Lcom/robtopx/geometryjump/GeometryJump;->getPackageName()Ljava/lang/String;

    move-result-object v1

    invoke-virtual {v0, v1}, Ljava/lang/StringBuilder;->append(Ljava/lang/String;)Ljava/lang/StringBuilder;

    move-result-object v0

    const-string v1, "/files/"

    invoke-virtual {v0, v1}, Ljava/lang/StringBuilder;->append(Ljava/lang/String;)Ljava/lang/StringBuilder;

    move-result-object v0

    invoke-virtual {v0}, Ljava/lang/StringBuilder;->toString()Ljava/lang/String;

    move-result-object v0

    invoke-static {v0}, Lcom/robtopx/geometryjump/GeometryJump;->LoadLibs(Ljava/lang/String;)V

    .line 19
    return-void
.end method
```

Add the code below to the main method.

```
.line 47
invoke-virtual {p0}, Lcom/robtopx/geometryjump/GeometryJump;->initMods()V
```

Then put what you downloaded to Smali. Compile the geometry dash and sign the apk.
As an example of a dynamic library, you can install [this mod](https://github.com/FlairyDash/rgb-icons-mod), put it to the GDModLoader folder that was created in the phone's memory.
