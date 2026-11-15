# Vloženie Unity projektu do repa (jednorazovo, Matúš)

Unity Hub nevie vytvoriť nový projekt do neprázdneho priečinka, preto:

1. V Unity Hub vytvor nový projekt **mimo repa** (šablóna podľa dohody, napr. *Universal 2D*).
2. Nastav: *Edit → Project Settings → Editor → Version Control Mode: Visible Meta Files*, *Asset Serialization Mode: Force Text*.
3. Zavri Unity.
4. Skopíruj z vytvoreného projektu do `Unity/` v repe **iba** priečinky `Assets/`, `Packages/`, `ProjectSettings/`.
   (`Library/`, `Temp/`, `Logs/`, `UserSettings/` nekopíruj.)
5. Unity Hub → *Add → Add project from disk* → `Unity/`.
6. V `Assets/` vytvor `_Stopa/` s podpriečinkami `Scripts/ Scenes/ Prefabs/ Art/ Audio/ Localization/`.
7. Do `README.md` doplň presnú verziu Unity (je v `ProjectSettings/ProjectVersion.txt`).
8. Commit + Push cez GitHub Desktop. Tento súbor potom môžeš zmazať.

Voliteľne – Unity Smart Merge (menej konfliktov v scénach a prefaboch), do `.git/config` lokálne:

```
[merge "unityyamlmerge"]
    name = Unity SmartMerge
    driver = '<cesta k Unity>/Editor/Data/Tools/UnityYAMLMerge.exe' merge -p %O %B %A %A
    recursive = binary
```
