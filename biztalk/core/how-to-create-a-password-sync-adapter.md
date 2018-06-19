---
title: Cómo crear un adaptador de sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249372"
---
# <a name="how-to-create-a-password-sync-adapter"></a>Cómo crear un adaptador de sincronización de contraseña
Un adaptador de sincronización de contraseñas (PS) es una aplicación que utiliza el componente Aplicación auxiliar de sincronización de contraseñas para pasar notificaciones a inicio de sesión único empresarial (SSO) y recibirlas de éste. Tenga en cuenta que aunque el componente Aplicación auxiliar de PS exponga una interfaz COM y .NET Framework, el adaptador no tiene por qué ser un componente COM. Puede diseñar el adaptador como un proceso independiente, una aplicación COM+ o un servicio de Windows.  
  
### <a name="to-create-a-password-sync-adapter"></a>Para crear un adaptador de sincronización de contraseñas  
  
1.  Informar al servicio de inicio de sesión único empresarial (ENTSSO) que el proveedor está utilizando active `ISSOPSWrapper.InitializeAdapter`.  
  
     `InitializeAdapter`informa a ENTSSO que se encuentra activado un proveedor, normalmente el mismo proveedor que realiza la llamada, y, por lo tanto, estará enviando actualizaciones de contraseñas hacia y desde el sistema. También puede usar `InitializeAdapter` para activar otros recursos, como adaptadores de grupo.  
  
2.  Enviar actualizaciones de contraseñas a ENTSSO mediante `ISSOPSWrapper.SendNotification`.  
  
     Debe determinar cómo recibe las actualizaciones de contraseña de su sistema ajeno a Windows. Después de recibir la actualización, puede pasar la información a ENTSSO mediante `SendNotification`. Tenga en cuenta que `SendNotification` no se limita a enviar actualizaciones de contraseñas: la arquitectura de `SendNotification` también le permite enviar otros tipos de notificaciones.  
  
3.  Solicitar actualizaciones de contraseñas de ENTSSO mediante `ISSOPSWrapper.ReceiveNotification`.  
  
     ENTSSO nunca llama a su adaptador ya que el adaptador de sincronización de contraseñas utiliza una tecnología de extracción. En su lugar, el adaptador llama periódicamente a `ReceiveNotification` para ver si están disponibles las actualizaciones de contraseña. La marca WAIT se puede configurar en `ReceiveNotification`. Al configurar WAIT se bloquea el subproceso hasta que haya una notificación disponible.  
  
     Tenga en cuenta que ENTSSO proporciona a su adaptador un cambio de contraseña en texto sin formato. Es responsabilidad del adaptador proteger la información referente a las contraseñas de una revelación incorrecta. También es responsabilidad del adaptador protegerse así mismo contra suplantaciones o ataques de otros orígenes no válidos, incluidas las suplantaciones del componente Aplicación auxiliar de sincronización de contraseñas.  
  
     Una vez que reciba una actualización de contraseñas de ENTSSO mediante el parámetro `pReceiveNotification`, debe pasar esta información a su sistema ajeno a Windows. Al igual que con `SendNotification`, debe determinar la mejor manera de comunicarse con el servidor remoto.  
  
4.  Desactivar el adaptador mediante `ISSOPSWrapper.ShutdownAdapter`.  
  
     `ShutdownApplication`debe ser el último método llamado por un adaptador e indica que el adaptador ya no enviará o recibirá actualizaciones de contraseñas a ENTSSO.  
  
     Tenga en cuenta que ENTSSO almacena en búfer todos los cambios de contraseñas que realice un usuario mientras que el adaptador permanezca desactivado, teniendo en cuenta el límite del tamaño del búfer.  
  
## <a name="see-also"></a>Vea también  
 [Programar con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)   
 [Sincronización de contraseñas](../core/synchronizing-passwords.md)