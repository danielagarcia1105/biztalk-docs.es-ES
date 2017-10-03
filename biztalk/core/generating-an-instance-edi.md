---
title: Generar una instancia (EDI) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5696d1590859469b10def4a42c955ff098819d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generating-an-instance-edi"></a>Generar una instancia (EDI)
Puede generar una instancia de mensaje desde un esquema EDI en el tiempo de diseño. Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 Puede generar un intercambio procesado por lotes completo (con intercambio y encabezados de grupo) o un conjunto de transacciones (sin intercambio ni encabezados de grupo). Si ejecuta la operación para generar un intercambio completo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un archivo con un encabezado de intercambio, un grupo para cada esquema y tres conjuntos de transacciones idénticos por grupo para cada esquema. Si ejecuta la operación para generar un conjunto de transacciones, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un archivo con un único conjunto de transacciones.  
  
 Para generar un intercambio procesado por lotes completo, ejecute el comando Generar instancia en el esquema por lotes. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] detectará los esquemas de mensaje en el proyecto e incluirá automáticamente los conjuntos de transacciones para esos esquemas.  
  
 Para generar un único conjunto de transacciones, ejecute el comando Generar instancia en un esquema de mensaje. En este caso, el esquema por lotes no necesita agregarse al proyecto. La instancia generada no incluirá un intercambio ni un encabezado de grupo, por lo que tendrá que agregarlos manualmente para tener un intercambio EDI funcional.  
  
 Cuando genere una instancia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará un cuadro de diálogo en el que se especifica la configuración usada en esa instancia, incluidos los separadores y el identificador de sintaxis.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a>Para generar una instancia de un intercambio procesado por lotes  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto. En el Explorador de soluciones, agregue un esquema de mensaje al proyecto para cada tipo de conjunto de transacciones que desee en la instancia de mensaje. Agregue el esquema de lote para el tipo de codificación al proyecto: Edifact_BatchSchema.xsd o X12_BatchSchema.xsd.  
  
    > [!NOTE]
    >  Los esquemas de lotes se encuentran en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.  
  
    > [!NOTE]
    >  No tiene que generar el proyecto para generar una instancia.  
  
2.  Haga clic en el esquema por lotes en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades** ventana, establezca **genere el tipo de salida de instancia** a **nativo** o **XML**. Seleccionar **nativo** le solicitará la generación de un archivo sin formato con una extensión. txt. Seleccionar **XML** le solicitará la generación de un archivo XML.  
  
4.  Para **nombre de archivo de instancia de salida**, escriba un nombre o vaya a un archivo y seleccione el archivo.  
  
    > [!NOTE]
    >  Si no especifica un valor para el nombre de archivo de la instancia de salida, se elegirá uno de forma automática. El nombre de archivo aparecerá en la ventana Salida de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
    > [!NOTE]
    >  Si selecciona un archivo existente, el contenido de éste se reemplazará por el contenido que genera esta operación.  
  
5.  Haga clic en el esquema por lotes y, a continuación, haga clic en **generar instancia**.  
  
6.  En el **propiedades de la instancia de EDI** cuadro de diálogo, seleccione los separadores, identificadores y otra configuración, las opciones para usarse en esa instancia y, a continuación, haga clic en **Aceptar**.  
  
7.  Compruebe que la operación ha funcionado en el **salida** ventana.  
  
8.  Para ver el archivo, presione **Control** y haga clic en el vínculo en el **salida** ventana. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]se mostrará el contenido del archivo en la ventana del Editor de BizTalk.  
  
    > [!NOTE]
    >  Al generar una instancia que contiene un 837I, 837d o 837p, el valor de GS08 se establecerá incorrectamente como 00401. Para obtener más información, consulte [problemas conocidos con herramientas de XML utilizadas con soluciones EDI](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a>Para generar una instancia de conjunto de transacciones  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto. Agregue el esquema del tipo de conjunto de transacciones para el que desea generar una instancia.  
  
    > [!NOTE]
    >  Para generar una instancia de conjunto de transacciones, no necesita agregar el esquema por lotes al proyecto.  
  
    > [!NOTE]
    >  No tiene que generar el proyecto para generar una instancia.  
  
2.  Haga clic en el esquema de mensaje en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.  
  
3.  En la ventana Propiedades, establezca **genere el tipo de salida de instancia** a **nativo** o **XML**. Seleccionar **nativo** le solicitará la generación de un archivo sin formato con una extensión. txt. Seleccionar **XML** le solicitará la generación de un archivo XML.  
  
4.  Para **nombre de archivo de instancia de salida**, escriba un nombre o vaya a un archivo y seleccione el archivo.  
  
    > [!NOTE]
    >  Si no especifica un valor para el nombre de archivo de la instancia de salida, se elegirá uno de forma automática. Se mostrará el nombre de archivo en el **salida** ventana de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
    > [!NOTE]
    >  Si selecciona un archivo existente, el contenido de éste se reemplazará por el contenido que genera esta operación.  
  
5.  Haga clic en el esquema de mensaje y, a continuación, haga clic en **generar instancia**.  
  
6.  En el **propiedades de la instancia de EDI** cuadro de diálogo, seleccione las opciones de configuración que desee y, a continuación, haga clic en **Aceptar**.  
  
7.  Compruebe que hay un mensaje en el **salida** ventana que indica que la operación se realizó correctamente.  
  
8.  Para ver el archivo, presione **Control** y haga clic en el vínculo en la ventana de salida. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]se mostrará el contenido del archivo en la ventana del Editor de BizTalk.  
  
9. Para crear un mensaje EDI funcional, agregue el intercambio y los encabezados de grupo al mensaje en un editor de texto.  
  
## <a name="see-also"></a>Vea también  
 [Uso de herramientas XML en tiempo de diseño](../core/using-design-time-xml-tools.md)   
 [Validar una instancia (EDI)](../core/validating-an-instance-edi.md)