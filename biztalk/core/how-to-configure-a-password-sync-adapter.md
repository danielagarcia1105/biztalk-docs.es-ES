---
title: "Cómo configurar un adaptador de sincronización de contraseña | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-password-sync-adapter"></a>Cómo configurar un adaptador de sincronización de contraseña
Cuando haya terminado de crear el adaptador de sincronización de contraseñas, debe cargarlo en un sistema. Asimismo, debe informar al inicio de sesión único empresarial (ENTSSO) y al almacén de configuración de que la aplicación es un adaptador de sincronización de contraseñas. Debe registrar con el almacén de configuración por motivos de seguridad: el adaptador solicitará actualizaciones de contraseñas y otras credenciales. Por lo tanto, ENTSSO debe saber que un determinado adaptador tiene autorización para pedir estos permisos.  
  
### <a name="to-configure-a-password-sync-adapter"></a>Para configurar un adaptador de sincronización de contraseñas  
  
1.  Cree el adaptador con el almacén de configuración mediante la herramienta ssops.  
  
     Al utilizar ssops, cargará un archivo de configuración XML en la base de datos de configuración que describe la aplicación en el inicio de sesión único empresarial.  
  
2.  Después de crear el adaptador con la base de datos de configuración, puede modificar la información del adaptador con `ISSOPSAdmin.SetAdapterProperties`.  
  
     Aunque los dos métodos son similares, `SetAdapterProperties` envía un mensaje al adaptador cuando cambia la información de configuración.  
  
3.  Para eliminar un adaptador, use ISSOAdmin.DeleteApplication.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/synchronizing-passwords.md)