# Useful Snippets for Banter V2 SDK


## Bullschript

Scene Settings

```
async function setSceneSettings() {
    const settings = new BS.SceneSettings();
    settings.EnableDevTools = false;
    settings.EnableTeleport = false;
    settings.EnableForceGrab = false;
    settings.EnableSpiderMan = true;
    settings.EnablePortals = true;
    settings.EnableGuests = true;
    settings.EnableQuaternionPose = false;
    settings.EnableControllerExtras = true;
    settings.EnableFriendPositionJoin = true;
    settings.EnableDefaultTextures = true;
    settings.EnableAvatars = true;
    settings.MaxOccupancy = 50;
    settings.RefreshRate = 72;
    settings.ClippingPlane = new BS.Vector2(0.05, 1000);
    settings.SpawnPoint = new BS.Vector4(0, 0.01, 0, 180);
    BS.BanterScene.GetInstance().SetSettings(settings);
};
setSceneSettings();
```
