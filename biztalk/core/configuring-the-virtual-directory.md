---
title: Configurar el directorio Virtual | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd87b89c6c23e709f21e78e3ea98dd2b84575ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-the-virtual-directory"></a>Configurar el directorio Virtual
En este tema se muestran los procedimientos para configurar el directorio virtual y verificar la aplicación para un usuario.  
  
## <a name="configuring-the-directory"></a>Configurar el directorio  
  
#### <a name="to-configure-the-virtual-directory"></a>Para configurar el directorio virtual  
  
1.  En %systemdrive%, cree una carpeta para configurarla como directorio virtual.  
  
2.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y haga clic en **Internet Information Services (IIS) Manager**.  
  
3.  Expanda  **\<nombre del servidor\>**  y, a continuación, expanda **sitios**.  
  
4.  Haga clic en **sitio Web predeterminado** y haga clic en **Agregar directorio Virtual**.  
  
5.  En el **Agregar directorio Virtual** diálogo cuadro, escriba el alias.  
  
6.  Escriba la ruta de acceso de la carpeta creada en el paso 1. O bien, haga clic en **(...)**  para ir a la ubicación de carpeta.  
  
7.  Haga clic en **Aceptar**. La carpeta se mostrará en el **sitio Web predeterminado** carpeta.  
  
8.  Haga clic en la carpeta y haga clic en **convertir en aplicación**.  
  
9. En el **Agregar aplicación** cuadro de diálogo, haga clic en **Aceptar**. La carpeta se convierte a una aplicación (puede ver el cambio en el icono, de un icono de carpeta al icono de sitio web).  
  
## <a name="verifying-an-application-for-a-user"></a>Comprobar una aplicación para un usuario  
 Las aplicaciones de los Servicios de Internet Information Server (IIS) se ejecutan con un elevado aislamiento; por lo tanto, debe verificar que la aplicación pueda ejecutarse en el contexto de un usuario del grupo Usuarios de hosts aislados de BizTalk mediante el uso del siguiente procedimiento.  
  
#### <a name="to-verify-an-application-for-a-user"></a>Para comprobar una aplicación para un usuario  
  
1.  En el Panel de Control, abra **herramientas administrativas**y, a continuación, haga clic en **servicios de componentes**.  
  
2.  Desplácese a la aplicación COM + en **servicios de componentes**.  
  
3.  Haga clic en la aplicación COM + y haga clic en **propiedades**.  
  
4.  Haga clic en **identificar** y cambie la identidad bajo la que se ejecuta esta aplicación COM + para un usuario que sea miembro de un grupo de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)