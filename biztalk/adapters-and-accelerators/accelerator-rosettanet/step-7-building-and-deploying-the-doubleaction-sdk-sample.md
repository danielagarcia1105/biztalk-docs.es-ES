---
title: 'Paso 7: Crear e implementar el ejemplo de SDK de DoubleAction | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9ebd9fe513e302c5bee83e902ed0d275c8785b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a>Paso 7: Crear e implementar el ejemplo de SDK de DoubleAction
El ejemplo DoubleAction.odx muestra cómo implementar una orquestación para generar respuestas automáticamente para los procesos de interfaz de socio (PIP) de doble acción 0C2, 0C4, 3A2 y 3A4. Puede extender este proyecto de ejemplo para admitir PIP de doble acción adicionales.  
  
 Use este ejemplo para enviar una respuesta automáticamente a Fabrikam siempre que Fabrikam realice una solicitud mediante uno de los cuatro PIP.  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a>Para compilar e inicializar el ejemplo de DoubleAction  
  
1.  En el equipo de Contoso, en una ventana del símbolo del sistema, desplácese a la carpeta siguiente:   
    *\<unidad\>*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.  
  
    > [!NOTE]
    >  Antes de ejecutar el programa de instalación, abra el archivo DoubleAction.sql (en la carpeta anterior) en el Bloc de notas. En el menú **Archivo** , haga clic en **Guardar como**. En el cuadro **Codificación** , seleccione **ANSI** en la lista desplegable y, a continuación, haga clic en **Guardar**. Seleccione **Sí** para sobrescribir el archivo existente.  
  
2.  Si la instalación de BizTalk Server se ejecuta en SQL Server 2008 R2 o 2008 SP1, ejecute setupx64.bat en la misma carpeta. El archivo por lotes realizará las acciones siguientes:  
  
    -   Crea un procedimiento almacenado de SQL (`PipAutomationGetAction`) en la base de datos BTARNDATA para recuperar el mensaje de acción de la tabla MessagesToLOB.  
  
    -   Compila el proyecto de .NET HeaderHelper y registra el ensamblado en la caché global de ensamblados.  
  
    -   Crea y enlaza la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (MessagesToLOB_Receive_Port) de puerto de recepción de SQL.  
  
    -   Habilita la ubicación de recepción (MessagesToLOB_Receive_Location).  
  
    -   Compila e implementa la orquestación PIPAutomation de doble acción (DoubleAction.odx).  
  
    -   Enlaza e inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
        > [!NOTE]
        >  El ejemplo muestra algunas advertencias durante la compilación. Puede omitir estas advertencias.  
  
        > [!NOTE]
        >  Compruebe que DoubleAction.odx se enlazó a **MessagesToLOB_Receive_Port**y que se inició la orquestación.  
  
3.  En la consola de administración de BizTalk Server, expanda el **grupo de BizTalk**, **aplicaciones**, y **BizTalk Application 1** nodos. Haga clic en el nodo **Orquestaciones** . Haga clic con el botón derecho en la orquestación **DoubleAction** y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo Propiedades, haga clic en el nodo **Enlaces** y, después, establezca el **Host** en **BizTalkServerApplication** y establezca el **Puerto de recepción** en **MessageToLOB_ReceivePort**. Haga clic en **Aceptar**. Haga clic con el botón derecho en la orquestación **DoubleAction** y, a continuación, haga clic en **Iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de la solución de Fabrikam](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)