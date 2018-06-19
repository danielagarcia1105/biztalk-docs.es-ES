---
title: Cómo configurar un archivo de clave de ensamblado de nombre seguro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec807cf6b596f7e89f607ebeb56700c59134c211
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968810"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>Cómo configurar un archivo de clave de ensamblado de nombre seguro
En el proceso de implementación de una solución de BizTalk, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] primero genera los ensamblados. El proceso de implementación necesita que cada ensamblado esté firmado de forma segura. Fuertemente puede firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro. Antes de implementar una solución desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] si aún no ha generado un archivo de clave de ensamblado de nombre seguro, use el procedimiento siguiente para ello y para asignarlo a cada proyecto de la solución.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Además, la cuenta debe tener permisos de escritura en la caché de ensamblados global (GAC). La cuenta de administradores del equipo local cuenta con este permiso.  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>Para configurar un archivo de clave de ensamblado de nombre seguro  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  En el símbolo del sistema, desde la carpeta donde desea almacenar el archivo de clave, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
     **sn /k***file_name* **.snk**   
  
     Ejemplo: **sn /k ErrorHandling.snk**  
  
     Un mensaje de confirmación, **escribe en el par de claves** \< *file_name*\>**.snk** `,` muestra en la línea de comandos.  
  
3.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **firma** y a **examinar** en el **elegir un archivo de clave de nombre seguro** cuadro de lista desplegable.  
  
5.  Busque el archivo de clave y haga clic en él. Haga clic en **abiertos**y, a continuación, cierre las propiedades del proyecto.  
  
6.  Repita los pasos del 3 al 6 para cada proyecto de la solución que desea implementar con este archivo de clave de ensamblado de nombre seguro.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)