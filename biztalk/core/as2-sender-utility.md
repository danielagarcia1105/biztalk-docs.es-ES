---
title: AS2 Utilidad del remitente | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69f70e2a404c92393fb02b301b58abf2d97da2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-sender-utility"></a>Utilidad del remitente de AS2
La utilidad del remitente de AS2 incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite enviar un mensaje AS2 a un sitio web en un único equipo. Esta utilidad simula el envío de un mensaje AS2 de un equipo diferente.  
  
 Los archivos de la utilidad del remitente de AS2 se encuentran en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="what-this-utility-does"></a>Qué hace esta utilidad  
 La utilidad del remitente de AS2 genera un mensaje AS2 con una carga EDI y envía ese mensaje a un sitio Web que utiliza el filtro ISAPI de BTSHTTPReceive. El tutorial realiza lo siguiente de forma predeterminada:  
  
-   Envía un mensaje AS2 con el nombre X12_00401_864.edi con una carga cifrada 864 X12. Este mensaje se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.  
  
-   Envía un MDN asíncrono en respuesta al mensaje AS2. Esto está determinado por el mensaje enviado y puede modificarse.  
  
-   Envía el mensaje AS2 a una ubicación de recepción a través del directorio virtual de Contoso.  
  
 La utilidad se puede modificar para cambiar este comportamiento específico. Consulte la [cómo personalizar la utilidad del remitente de AS2](../core/as2-sender-utility.md#BKMK_Custom) sección más adelante.  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a>Cómo configurar una solución mediante la utilidad del remitente de AS2  
 Para configurar una solución con el fin de utilizar la utilidad del remitente de AS2, necesita realizar lo siguiente.  
  
> [!IMPORTANT]
>  Estos pasos se muestran en el tutorial de AS2 y en los dos tutoriales sobre el envío de AS2. Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md), [tutorial (AS2): enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md), y [tutorial (AS2): enviar EDI a través de AS2 con un asincrónico MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).  
  
-   Habilite el filtro ISAPI de BTSHTTPReceive.  
  
-   Configure una página Web y una ubicación de recepción para recibir el mensaje de AS2. En la utilidad del remitente de AS2 predeterminada, la página Web es la de Contoso.  
  
-   Implemente el esquema para el intercambio EDI que vaya a enviar como carga del mensaje AS2.  
  
-   Establezca las propiedades de entidad de EDI y AS2.  
  
##  <a name="BKMK_Custom"></a>Cómo personalizar la utilidad del remitente de AS2  
 La utilidad del remitente de AS2 predeterminada envía un intercambio de prueba EDI 864 a través de AS2 a una página Web de Contoso mediante el filtro ISAPI de BTSHTTPReceive. El mensaje AS2, con el nombre X12_00401_864.edi, solicita un MDN asíncrono. El código de la utilidad del remitente de AS2 se encuentra en HttpSender.cs en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender. La siguiente línea de código de HttpSender.cs envía el archivo de prueba 864:  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  Puede modificar esta línea con un nombre de archivo distinto y una ruta diferente.  
  
 La siguiente línea en HttpSender.cs envía un mensaje de AS2 con el nombre X12_00401_864-Sync.edi. Este mensaje solicita un MDN sincrónico. De forma predeterminada, se hace referencia a esta línea de código en HttpSender.cs en favor de la línea que envía X12_00401_864.edi. Para enviar X12_00401_864-Sync.edi, elimine el comentario de la línea X12_00401_864-Sync.edi y convierte en comentario la línea X12_00401_864.edi.  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 La siguiente línea de código en HttpSender.cs envía el mensaje a la página web de Contoso:  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  Puede modificar esta línea con un filtro ISAPI y un directorio virtual distinto.  
  
### <a name="to-build-the-as2-sender-sample"></a>Para generar el ejemplo del remitente de AS2  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto Sender.csproj en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.  
  
2.  Abra HttpSender.cs en el proyecto del remitente y personalice el código del remitente con la página Web de recepción apropiada y la ruta y nombre de archivo EDI apropiados.  
  
3.  Haga clic en el proyecto del remitente y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en **firma** en la consola de la izquierda. Asegúrese de que **firmar el ensamblado** está seleccionada, y el archivo de clave de nombre seguro se establece en **Sender.snk**. Asegúrese de que **Retrasar firma sólo** está desactivada.  
  
5.  Generar el proyecto.  
  
### <a name="to-run-the-as2-sender-sample"></a>Para ejecutar el ejemplo del remitente de AS2  
  
1.  Abra un símbolo del sistema. Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.  
  
2.  ENTRAR **Sender.exe**y, a continuación, presione **ENTRAR**.  
  
3.  Compruebe que visualiza un mensaje que indica que un mensaje AS2 se ha enviado correctamente y, a continuación, cierre el símbolo de sistema.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)   
 [Tutorial (AS2): Enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)   
 [Tutorial (AS2): Enviar EDI a través de AS2 con un MDN asíncrono](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)