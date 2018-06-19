---
title: 'Paso 9: Probar la solución EDI | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6e308ae230ea2d78ff03ed02a81310c38fbcabc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278652"
---
# <a name="step-9-test-the-edi-solution"></a>Paso 9: Probar la solución EDI
![Paso 9 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 Este tema le permite probar el procesamiento de entrada y ver el informe Estado de intercambio de EDI correspondiente a la información de procesamiento.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="testing-the-solution"></a>Probar la solución  
  
1.  En el Explorador de Windows, vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations. Copia la **SamplePO.txt** archivo.  
  
2.  Pegar la **SamplePO.txt** el archivo en el [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM carpeta.  
  
3.  Vaya a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem. Compruebe que haya un archivo de salida con formato de texto (txt) en la carpeta.  
  
4.  Abra el archivo de salida [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem y el archivo de entrada SamplePO.txt en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations. Compruebe que los datos en el mensaje de salida se corresponden con los datos de la versión original **SamplePO.txt** archivo.  
  
    > [!NOTE]
    >  Para verificar si los datos del archivo de salida se han transformado con respecto a los datos del archivo de entrada, abra el archivo Inbound4010850_to_OrderFile.btm en Visual Studio y compruebe las asignaciones.  
  
5.  Vaya a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997. Compruebe si hay un archivo de confirmación 997 de salida en formato de texto en la carpeta en el que el elemento de datos ST01 sea "997".  
  
6.  En el árbol de consola de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **grupo de BizTalk**. En la parte inferior del panel derecho, haga clic en **intercambio EDI y estado de confirmación correlacionado**.  
  
7.  En la expresión de consulta, cambie el operador para la **estado** campo **es igual a** y cambie el **valor** field para la **estado** campo **Todos los**. Eliminar el **campo de fecha y hora de intercambio** (seleccione la fila y presione SUPR en el teclado).  
  
8.  Haga clic en **Ejecutar consulta**.  
  
9. Verifique si se muestran dos mensajes en el informe de estado: uno en la dirección de recepción de ELLOS (Fabrikam) a NOSOTROS (OrderSystem) (mensaje 850); el otro, en la dirección de envío de NOSOTROS (OrderSystem) a ELLOS (Fabrikam) (confirmación 997).  
  
10. Haga doble clic en el mensaje de ELLOS a NOSOTROS. En el **estado y los detalles de la confirmación del intercambio** diálogo cuadro, compruebe que se muestran los detalles del intercambio en el panel derecho.  
  
11. Haga clic en **confirmaciones funcionales**. Compruebe si los detalles del informe de la confirmación se muestran en el panel derecho.  
  
12. Cierre el cuadro de diálogo Detalles de la confirmación y del estado de intercambio.  
  
13. En el **estado de confirmación y del intercambio** panel, haga clic en el mensaje de ellos a nosotros y, a continuación, haga clic en **detalles de conjunto de transacciones**. Haga clic en la entrada en el **resultados de la consulta** panel y, a continuación, haga clic en **contenido de conjunto de transacciones de vista**. Compruebe que los datos del conjunto de transacciones se muestra en el **detalles del mensaje** cuadro de diálogo. En el Explorador de Windows, abra el archivo SamplePO.txt en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations. Compruebe que el conjunto de transacciones se muestra en el **detalles del mensaje** cuadro de diálogo es el mismo que en el mensaje de entrada, sin los encabezados de grupo y de intercambio y los finalizadores.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ha completado el tutorial de programadores de la interfaz EDI.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Tutorial de desarrollador de la interfaz EDI](../core/tutorial-2-edi-interface-developer-tutorial.md)   
 [Paso 1: Preparar el Tutorial de programadores de la interfaz EDI](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)