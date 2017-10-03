---
title: Validar una instancia (EDI) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cceea8afe67f7e69b3ee842198d9a5373a972d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validating-an-instance-edi"></a>Validar instancias (EDI)
Las instancias pueden validarse con respecto a su esquema EDI en el tiempo de diseño. Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. La instancia que valide puede ser un único conjunto de transacciones (sin intercambio ni encabezados de grupo), un intercambio con un único conjunto de transacciones (con intercambio y encabezados de grupo) o un intercambio procesado por lotes completo con varios conjuntos de transacciones (con intercambio y encabezados de grupo).  
  
> [!NOTE]
>  Validación de un intercambio conservado XML no es compatible. Sin embargo, la validación de un intercambio conservado EDI sí es compatible.  
  
 La operación de validar instancia realiza tanto la validación EDI como la XSD.  
  
 Cuando se valida una instancia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] muestra un cuadro de diálogo en el que se especifica la configuración que se va a validar en ella, incluidos los separadores y el identificador de sintaxis.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-validate-an-instance-against-its-schema"></a>Para validar una instancia con respecto a su esquema  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.  
  
2.  En el Explorador de soluciones, agregue al proyecto todos los esquemas necesarios para la instancia del mensaje.  
  
    1.  Si valida un único conjunto de transacciones sin intercambio ni encabezados de grupo, agregue el esquema de documento para ese conjunto de transacciones.  
  
    2.  Si valida un intercambio con un único conjunto de transacciones, agregue al proyecto el esquema para la transacción y el esquema de lote para el tipo de codificación que se usa en el mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).  
  
        > [!NOTE]
        >  El esquema de lote es necesario para validar el sobre de la instancia. Si usara únicamente el esquema de mensaje, el sobre no se validaría.  
  
    3.  Si va a validar un intercambio por lotes con varios conjuntos de transacciones, agregue al proyecto los esquemas para cada grupo de conjuntos de transacciones en la instancia de mensaje y el esquema de lote para el tipo de codificación que se usa en el mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).  
  
        > [!NOTE]
        >  Si ha personalizado el esquema de servicios, tendrá que incluir el esquema de servicio personalizado en el proyecto de BizTalk, además de los esquemas de documento (conjunto de transacciones) y, si es necesario, el esquema por lotes.  
  
        > [!NOTE]
        >  No tiene que generar el proyecto para validar una instancia.  
  
3.  Para que la página de propiedades del esquema aparezca en el Explorador de soluciones, haga lo siguiente:  
  
    1.  Si va a validar un único conjunto de transacciones, haga clic en el esquema de documento para ese conjunto de transacciones y, a continuación, haga clic en **propiedades**.  
  
    2.  Si va a validar un intercambio con un único conjunto de transacciones o un intercambio por lotes con varios conjuntos de transacciones, haga clic en el esquema por lotes (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd esquema) y, a continuación, haga clic en **propiedades**.  
  
4.  En la ventana Propiedades para el esquema, para **nombre de archivo de instancia de entrada** escriba el nombre y la ruta de acceso de la instancia de mensaje que se desea validar, o busque el archivo, selecciónelo y, a continuación, haga clic en **Aceptar**.  
  
5.  Para **valide el tipo de entrada de instancia**, escriba el tipo de archivo que va a validar: **nativo** para los archivos EDI o **XML** para un archivo XML.  
  
    > [!NOTE]
    >  Validación de un intercambio conservado XML no es compatible. Si selecciona XML para el **valide el tipo de entrada de instancia** propiedad cuando se valida un intercambio conservado, se producirá un error en la operación y se devolverá nada. Sin embargo, si selecciona **nativo** para el **valide el tipo de entrada de instancia** al validar un intercambio conservado, la operación se realizará correctamente.  
  
6.  Haga clic en el esquema de mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd si va a validar un intercambio con un único conjunto de transacciones o un intercambio por lotes) y, a continuación, haga clic en **Validar instancia**.  
  
7.  En el **propiedades de la instancia de EDI** diálogo cuadro, realice lo siguiente:  
  
    1.  Si la instancia debe utilizar un separador de repeticiones, seleccione **separador de repeticiones**.  
  
    2.  Si la instancia debe utilizar delimitadores finales, seleccione **Sí** para **usar delimitadores finales**.  
  
    3.  Si la instancia debe utilizar un conjunto distinto de caracteres **básica**, seleccione **extendido** o **Unicode** en **identificador de sintaxis**.  
  
    4.  Haga clic en **Aceptar**.  
  
        > [!NOTE]
        >  El **propiedades de la instancia de EDI** cuadro de diálogo puede aparecer una segunda vez después de que haya hecho clic **Aceptar**. Si es así, haga clic en **Aceptar** nuevo.  
  
        > [!NOTE]
        >  El **propiedades de la instancia de EDI** cuadro de diálogo se llenará con los mismos valores usados en la última operación de validar instancia que se ha ejecutado para el mismo usuario ha iniciado la sesión.  
  
8.  Compruebe que hay un mensaje en el **salida** ventana que indica que la operación se realizó correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Uso de herramientas XML en tiempo de diseño](../core/using-design-time-xml-tools.md)   
 [Generar una instancia (EDI)](../core/generating-an-instance-edi.md)