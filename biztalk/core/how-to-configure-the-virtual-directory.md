---
title: "Cómo configurar el directorio Virtual | Documentos de Microsoft"
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
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97af99271a4d63046d2a95a47caed7f145eaef24
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-virtual-directory"></a>Cómo configurar el directorio Virtual
En este tema se describen los procedimientos para configurar el directorio virtual y verificar la aplicación para un usuario.  
  
### <a name="to-configure-the-virtual-directory"></a>Para configurar el directorio virtual  
  
1.  En %systemdrive%, cree una carpeta para configurarla como directorio virtual.  
  
2.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y haga clic en **Internet Information Services (IIS) Manager**.  
  
3.  Expanda  **\<nombre del servidor >** y, a continuación, expanda **sitios**.  
  
4.  Haga clic en **sitio Web predeterminado** y haga clic en **Agregar directorio Virtual**.  
  
5.  En el **Agregar directorio Virtual** diálogo cuadro, escriba el alias.  
  
6.  Escriba la ruta de acceso de la carpeta creada en el paso 1. O bien, haga clic en **(...)**  para ir a la ubicación de carpeta.  
  
7.  Haga clic en **Aceptar**. La carpeta se mostrará en el **sitio Web predeterminado** carpeta.  
  
8.  Haga clic en la carpeta y haga clic en **convertir en aplicación**.  
  
9. En el **Agregar aplicación** cuadro de diálogo, haga clic en **Aceptar**. La carpeta se convierte a una aplicación (puede ver el cambio en el icono, de un icono de carpeta al icono de sitio web).  
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)