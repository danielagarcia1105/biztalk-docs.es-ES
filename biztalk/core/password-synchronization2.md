---
title: Contraseña Synchronization2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264364"
---
# <a name="password-synchronization"></a>Sincronización de contraseña
El propósito de la característica Sincronización de contraseñas es simplificar la administración de la base de datos de SSO y mantener las contraseñas sincronizadas entre directorios de usuario.  
  
 Estas dos tareas se llevan a cabo mediante el uso de adaptadores de sincronización de contraseñas, y los temas de esta sección explican la utilidad de línea de comandos para crear y administrar esos adaptadores.  
  
 Hay tres tipos de subcaracterísticas de sincronización de contraseñas.  
  
 El primer tipo es **Windows a externo** (por ejemplo, Active Directory a RACF). En este escenario, se captura un cambio de contraseña de usuario de Windows y se envía al servidor de SSO empresarial asignado para recibir cambios de contraseña de controladores de dominio. Después se reenvía el cambio de contraseña a un sistema externo y la asignación en la base de datos de SSO se mantiene en sincronización con el cambio realizado en el sistema externo.  
  
 El segundo tipo es **externo a Windows, sincronización completa**. En este escenario, se captura una contraseña en el sistema externo y se envía al servidor de inicio de sesión único empresarial asignado para la sincronización de contraseñas, que a su vez actualiza la contraseña en la base de datos de SSO, y también actualiza la contraseña de usuario de Windows en Active Directory.  
  
 El tercer tipo es **externo a Windows, sincronización parcial**. En este escenario, se captura una contraseña en el sistema externo y se envía al servidor de inicio de sesión único empresarial asignado para la sincronización de contraseñas, que a su vez actualiza la contraseña en la base de datos de SSO.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo instalar la sincronización de contraseña](../core/how-to-install-password-synchronization.md)  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-administer-password-synchronization.md)  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Cómo administrar la sincronización de contraseña](../core/how-to-manage-password-synchronization.md)