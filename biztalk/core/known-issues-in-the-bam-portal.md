---
title: Problemas conocidos con el Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cbfa298590c62b359045b6c7372501d8ef397e
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710759"
---
# <a name="known-issues-in-the-bam-portal"></a>Problemas conocidos del portal de BAM
Este tema contiene información que le ayudará a identificar y resolver los problemas que pueden surgir al usar el portal de BAM.  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a>Se producen errores cuando el Portal de BAM e Internet Explorer están en el mismo equipo y la configuración de seguridad baja  
 **Problema**  
  
 Al usar Internet Explorer, puede aparecer el mensaje de error **Error de servidor en ' / BAM' aplicación** en las siguientes circunstancias:  
  
-   Al hacer clic en una actividad relacionada que remite a una instancia de actividad inexistente.  
  
-   Al hacer clic en el **guardar alerta** botón en el siguiente escenario:  
  
    -   Crear una consulta en el **búsqueda de actividad económica** página y, a continuación, haga clic en **establecer alerta**.  
  
    -   Complete los campos de alerta y, a continuación, haga clic en **guardar alerta**.  
  
    -   Hace clic en el botón Atrás.  
  
    -   Hacer clic en el **guardar alerta** nuevamente en el botón.  
  
 **Cause**  
  
 Cuando se ejecuta Internet Explorer con el nivel de seguridad establece bajo, las solicitudes Web se ejecutan con pocos privilegios. Para afrontar el desafío de la seguridad integrada de Windows, Internet Explorer pasa un token de usuario con muy pocos privilegios.  
  
 Si se está usando Internet Explorer en el mismo equipo en que está instalado el portal de BAM, y se establece el nivel de seguridad de Internet Explorer como bajo, el portal actúa como el usuario con el token de pocos privilegios. Dicho token no concede permisos de escritura en el registro de eventos. Cuando detecta un error, el portal intenta registrarlo en el registro de eventos; esto le hará generar un error, ya que los privilegios reducidos del token de usuario son insuficientes para tener acceso al registro de eventos.  
  
 **Resolución**  
  
 Si necesita explorar desde el equipo local, debe agregar http://localhost a la lista de sitios de confianza.  
  
#### <a name="add-localhost-to-the-list-of-trusted-sites"></a>Agregar host local a la lista de sitios de confianza  
  
1.  En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.  
  
2.  Haga clic en el **seguridad** ficha y, a continuación, haga clic en **sitios de confianza** en el **seleccione una zona para ver o cambiar la configuración de seguridad** ventana.  
  
3.  Haga clic en el **sitios** botón.  
  
4.  En el **agregar este sitio Web a la zona** cuadro de texto, escriba **http://localhost**. Si el **Requerir comprobación del servidor (https:) para todos los sitios de esta zona** casilla de verificación está activada, desactívela y, a continuación, haga clic en el **agregar** botón. El sitio, http://localhost, aparecerá en la **sitios Web** lista.  
  
5.  Si es necesario, restaure la **Requerir comprobación del servidor (https:) para todos los sitios de esta zona** casilla de verificación a su estado original.  
  
6.  Haga clic en el **cerrar** botón y, a continuación, haga clic en **Aceptar**.  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer"></a>Las agregaciones del Portal de BAM no llenarán los datos existentes cuando se usa una dirección IP como una dirección URL en Internet Explorer
 **Problema**  
  
 Cuando se usa una dirección IP como una dirección URL con Internet Explorer para ver el portal de BAM, las agregaciones muestran el siguiente mensaje: "sin detalles. No se ha podido procesar la consulta."  
  
 **Cause**  
  
 La configuración de seguridad predeterminada en Internet Explorer puede impedir el acceso a sitios que utilizan direcciones IPv4 e IPv6 como direcciones URL.  
  
 **Resolución**  
  
 Agregue la dirección del sitio a la lista de sitios de confianza y habilite el acceso a los orígenes de datos entre dominios.  
  
#### <a name="add-the-ip-address-to-the-trusted-sites-list"></a>Agregar la dirección IP a la lista de sitios de confianza  
  
1.  En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.  
  
2.  Haga clic en el **seguridad** ficha y, a continuación, haga clic en el **sitios de confianza** zona de seguridad.  
  
3.  Haga clic en el **sitios** botón.  
  
4.  En **agregar este sitio Web a la zona**, escriba la dirección IP del portal de BAM y, a continuación, haga clic en **agregar**.  
  
5.  Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
#### <a name="enable-access-to-data-sources-across-domains"></a>Habilitar el acceso a orígenes de datos entre dominios  
  
1.  En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.  
  
2.  Haga clic en el **seguridad** ficha y, a continuación, haga clic en el **sitios de confianza** zona de seguridad.  
  
3.  Haga clic en el **nivel personalizado** botón mientras se desplaza hacia abajo hasta la **varios** nodo de la **configuración** árbol.  
  
4.  En el **acceder a orígenes de datos a través de dominios** nodo, haga clic en el **habilitar radio** botón y, a continuación, haga clic en **Aceptar**.  
  
## <a name="bmexe-does-not-run-in-powershell"></a>BM.exe no se ejecuta en PowerShell  
 **Problema**  
  
 El siguiente comando produce un error al ejecutarse en PowerShell.  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 **Cause**  
  
 PowerShell no ha podido localizar la ruta de los archivos .exe y config.  
  
 **Resolución**  
  
 Si usa bm.exe en PowerShell, especifique la ruta completa de los archivos .exe y config. Por ejemplo: `bm.exe get-config -FileName:config.xml` debe especificarse como `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.  
  
## <a name="see-also"></a>Vea también  
 [Planificar para el portal de BAM](../core/planning-for-the-bam-portal.md)