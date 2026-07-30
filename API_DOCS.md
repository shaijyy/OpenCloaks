---
title: basic api documentation
description: how to use OpenCloaks's OptiFine-supported API
---

> **Note**  
> OpenCloaks implements the OptiFine cosmetics protocol.  
> The endpoint layout intentionally matches the protocol used by OptiFine clients for compatibility purposes only.

# API docs

## Cosmetics
### Capes
**GET** ```/capes/{username}.png```  
Returns cape texture of player `{username}`  
Fallback to default (/capes/default.png) if no cape is available.

### Items
**GET** ```/items/{cosmetic}/users/{username}.png```  
Validates* player `{username}` has cosmetic `{cosmetic}` available (equippable) then returns its texture.  
Historically, the protocol exposed textures through per-user paths, thus the weirdly structured endpoint.  
*Validation not implemented yet

**GET** ```/items/{cosmetic}/model.cfg```  
Returns the PlayerItem model definition for cosmetic `{cosmetic}`.  

### User Configuration
**GET** ```/users/{username}.cfg```  
Returns JSON-formatted list of active items and data for player `{username}`.

### To Be Implemented (does not exist)
**POST** ```/users/{username}/cape```  
With new cape texture payload, updates player `{username}` configuration to use newly declared cape

**GET** ```/items/available/{username}.cfg```  
Returns JSON-formatted list of available (equippable) items for player `{username}`

## Compatibility
The OpenCloaks API is compatible with clients and game modifications implementing the OptiFine cosmetics protocol.  
This project is independent and is not affiliated with OptiFine, or Mojang.
