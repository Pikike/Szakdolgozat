# ASSIMP-UE-demo-tutorial
# Telepítési útmutató Unreal Engine 4.27-hez

Az alábbi telepítési útmutató részletesn leírja, hogy miket kell telepíteni, vagy módosítani a játék működéséhez.

## Első lépések
Miután a projekt le lett klónozva, el kell navigálni a projekt gyökérkönyvárából a Plugins mappába, aminek az útvonala:
AssimpProjekt\Plugins

Ha a Plugins mappa üres, akkor a továbbiakban az Assimp plugin fordítása bekezdést kell végrehajtani, majd a Játékok elérésével kell folytatni. Ha az Plugins mappában találhatóak fájlok, akkor elegendő a Játékok elérésével folytatni.

## Assimp plugin fordítása

Az Assimp plugint az alábbi útmutató segítségével lehet hozzáadni a projekthez:
- Először meg kell nyitni az .uprojekt fájlt és hozzá kell adni egy C++ osztályt. Ezt a File/New C++ Class menüből lehet kiválasztani, majd a szülő osztálynak a None-t kell választani, így lesz egy üres C++ osztályunk. Ha az osztály létrejött megnyílik egy Visual Studio ablakban, és az Unreal Engine-t be is lehet egyenlőre zárni.
- A Plugins mappából Git Bash segítségével ki kell adni az alábbi parancsot:

    ``` git clone --recurse-submodules https://github.com/irajsb/UE4_Assimp/ ```
- Ha nem látszik a Git Bash opció, akkor telepíteni kell a Gitet a hivatalos Git weboldalról.
- Az előző lépés sikeres volt, ha Plugins könyvtár megtelik fájlokkal: ha a következő könyvtár megtelik fájlokkal:
Plugins\UE4_Assimp\Source\ThirdParty\UE_AssimpLibrary\assimp
- A fenti elérési utvonallal megadott könyvtárból terminál segítségével ki kell adni az alábbi parancsot:

    ``` cmake CMakeLists.txt -DLIBRARY_SUFFIX:STRING=```
- Ezután a generált fájlt ( windows platformon .sln) fájlt meg kell nyitni
-Itt ki kell választani a  Release build configuration x64 opciót és le kell fordítani a projektet.
- Végül a projekt gyökerében lévő .sln fájlt is le kell fordítani.

## Játékok elérése
Az AssimpProjekt.uproject megnyitása után el kell navigálni az Content Browser-ben a következő mappába: Content/Assimp/JatekElem. Itt a DTJatekElem adattáblát kell megnyitni. Itt a tábla path oszlobában lévő értékeket kell kiegészíteni a leklónozott projekt elérési útvonalával. Ezt az első '\\' jel elé kell írni. Majd a tábla mentése után futtatható is a játék. 

  


    
