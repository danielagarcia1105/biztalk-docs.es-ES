---
title: "Paso 11: Probar la solución AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 490833859717ec37e0cb53ae89497aa361adda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-test-the-as2-solution"></a>Paso 11: Probar la solución AS2
![Paso 11 de 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")  
  
 En este paso se comprueban los resultados de este tutorial.  
  
 Necesita generar el archivo Sender.exe que utiliza para enviar un mensaje EDI en la ubicación de recepción Receive_AS2 (a través del directorio virtual de Contoso). Sender.exe devuelve un mensaje MDN asíncrono. El archivo de mensaje es X12_00401_864.edi ubicado en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a>Para probar la solución con un mensaje EDI asíncrono  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto Sender.csproj en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender. Haga clic en el proyecto del remitente y, a continuación, haga clic en **propiedades**. Haga clic en **firma** en la consola de la izquierda. Asegúrese de que **firmar el ensamblado** esté seleccionada y establece el archivo de clave de nombre seguro en **Sender.snk**. Asegúrese de que **Retrasar firma sólo** está desactivada.  
  
2.  Generar el proyecto.  
  
3.  Abra un símbolo del sistema y desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug. ENTRAR `Sender.exe`y, a continuación, presione **ENTRAR**. Compruebe que visualiza un mensaje que indica que un mensaje AS2 se ha enviado correctamente y, a continuación, cierre el símbolo de sistema.  
  
    > [!NOTE]
    >  Ejecución de compilaciones de Sender.exe un mensaje AS2 que contiene el siguiente intercambio de prueba de EDI: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 tutorial\x12_00401_864. Después de generar el mensaje AS2, lo registra en el directorio virtual de Contoso, que utiliza BTSHttpReceive.dll para enrutar el mensaje en la ubicación de recepción.  
  
4.  Navegue hasta la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\carpeta _MDNToFabrikam. Compruebe que hay un \<GUID > .msg archivo en la carpeta. Abra el archivo en el Bloc de notas y compruebe que el mensaje sea un MDN con AS2-From configurado en Contoso y AS2-To configurado en Fabrikam.  
  
5.  Navegue hasta la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso carpeta. Compruebe que hay un \<GUID > archivo .xml en la carpeta. Haga doble clic en el archivo y compruebe que el campo ST01 del mensaje se establece en 864.  
  
6.  Navegue hasta la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\carpeta _997ToFabrikam. Compruebe que hay un \<GUID > .msg archivo en la carpeta. Abra el archivo con el Bloc de notas y compruebe que el mensaje sea un mensaje 997 (con un ST1 de 997) con encabezados AS2 sobre una carga EDI. Compruebe que AS2-From es Contoso y AS2-To es Fabrikam. Compruebe que ISA6 (identificador de remitente) se establezca en 1234567 (Contoso) e ISA8 (identificador de receptor) se establezca en 7654321 (Fabrikam).  
  
7.  Para ver los informes de estado de AS2 y EDI, vaya a la **concentrador de grupo** página en la consola de administración de BizTalk Server, desplácese hasta la parte inferior de la página y haga clic en uno de los vínculos de informe de estado. Para obtener más información, consulte [EDI y los informes de estado de AS2](../core/edi-and-as2-status-reporting.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ha completado el tutorial de AS2.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)   
 [Paso 1: Preparar el Tutorial de AS2](../core/step-1-prepare-for-the-as2-tutorial.md)