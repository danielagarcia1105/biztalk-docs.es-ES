---
title: Extensión de BTARN con un PIP nuevo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0904d6d427fb6c04ae911edf23edb653ba9cb734
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003653"
---
# <a name="extending-btarn-with-a-new-pip"></a>Extensión de BTARN con un PIP nuevo
Este tema describe cómo ampliar Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] con un nuevo esquema de proceso de interfaz de socio (PIP). Esto le permite agregar un esquema basado en un PIP de RosettaNet cuando ese PIP no está asociado con cualquiera de los esquemas que se instalan con el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación.  

 Si extiende [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] con un PIP nuevo, implementa el nuevo esquema en su propio ensamblado. También puede modificar un esquema existente que se implementa dentro de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Rnpip ensamblado. Para obtener más información, consulte [modificar un PIP existente en Rnpip](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).  

### <a name="to-extend-btarn-with-a-new-pip"></a>Para ampliar BTARN con un PIP nuevo  

1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  

2. En el símbolo del sistema, vaya a \< *unidad*\>: \Program archivos\\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema Generator.  

3. En el símbolo del sistema, escriba **CScript InstallDTD.vbs**y, a continuación, presione **ENTRAR**.  

   > [!NOTE]
   >  Sólo tendrá que realizar los pasos del 1 al 3 una vez después de instalar a BizTalk Server.  

4. Inicie Visual Studio.  

5. En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  

6. En el cuadro de diálogo nuevo proyecto, seleccione **proyectos de BizTalk** en el panel izquierdo y, a continuación, haga clic en **proyecto vacío de servidor BizTalk** en el panel derecho.  

7. Haga clic en **examinar** y apuntar al directorio donde desea guardar el proyecto.  

8. En el **nombre** , escriba un nombre de proyecto, como **MyCustomPIP**y, a continuación, haga clic en **Aceptar**.  

9. Inicie el símbolo del sistema de Visual Studio.  

10. En el símbolo del sistema, desplácese a la ubicación especificada en el paso 7, tipo **sn -k \<proyecto name.snk\>** y, a continuación, presione **ENTRAR**.  

11. En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.  

12. En el **páginas de propiedades** cuadro de diálogo, haga clic en **ensamblado** en **propiedades comunes** en el panel izquierdo.  

13. En el panel derecho, desplácese hacia abajo hasta **Strong Name**, haga clic en **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...) en el panel derecho. Vaya a la ubicación especificada en el paso 7 y seleccione el nombre del archivo .snk creado en el paso 10.  

14. En el cuadro de diálogo páginas de propiedades, expanda **propiedades de configuración**y, a continuación, haga clic en **implementación**. En el panel derecho, haga clic en **volver a implementar**, seleccione `True`y, a continuación, haga clic en **Aceptar**.  

15. En el Explorador de soluciones, haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  

16. En el **Agregar elemento existente** cuadro de diálogo, desplácese a \< *unidad*\>: \Program archivos\\seleccione Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas, **xml.xsd**, a continuación, haga clic en **agregar**.  

17. Descargue el PIP que se va a ampliar los Rnpip con RosettaNet.org. Para obtener más información, consulte [incorpora un nuevo proceso de interfaz de socio](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).  

18. En el Explorador de soluciones, expanda el nombre del proyecto, haga clic en **referencia**y, a continuación, haga clic en **Agregar referencia**.  

19. En el **Agregar referencia** cuadro de diálogo, haga clic en **examinar**y mover a \< *unidad*\>: \Program archivos\\Microsoft BizTalk 2013 Acelerador para RosettaNet\Bin y, a continuación, seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**. Haga clic en **abierto**y, a continuación, haga clic en **Aceptar**.  

20. En el Explorador de soluciones, haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

21. En el **agregar elementos generados** cuadro de diálogo el **categorías** panel, haga clic en **generar esquemas**. En el **plantillas** panel, haga clic en **generar esquemas**y, a continuación, haga clic en **agregar**.  

22. En el cuadro de diálogo Generar esquemas, realice lo siguiente:  


    |     Use      |                                                                    Para                                                                    |
    |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Tipo de documento** |                                                              Seleccione **esquema DTD**.                                                              |
    |  **Archivo de entrada**   | Haga clic en **examinar**, vaya a la carpeta que contiene el archivo DTD de RosettaNet.org, seleccione el archivo DTD que desee y, a continuación, haga clic en **abierto**. |


23. En el cuadro de diálogo Generar esquemas, haga clic en **Aceptar**.  

24. En el Explorador de soluciones, haga doble clic en el archivo .xsd que acaba de importar.  

25. En el Editor de BizTalk, seleccione el \< *esquema* \> nodo.  

26. En la ventana Propiedades, desplácese hacia abajo hasta **tipo de documento**. En el **tipo de documento** cuadro, **PIP**\<*código de tres dígitos*\>, por ejemplo, **PIP3A2**. En el **versión del documento** , escriba **v**\<*xx.xx* \> o **R** \< *xx.xx*\>, por ejemplo, **R01.02**. Esta versión debería ser como se documenta en la especificación de PIP de RosettaNet.  

27. En la ventana Propiedades, desplácese hacia abajo hasta **referencia raíz**. Haga clic en **referencia raíz**y en la lista desplegable, seleccione el nodo raíz del esquema, por ejemplo, seleccione **Pip3C5BillingStatementNotification**.  

28. En la ventana Propiedades, desplácese hasta **Target Namespace**. Para **Target Namespace**, tipo  <strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD nombre de archivo\>.dtd</strong>, donde es el nombre del archivo DTD, por ejemplo, **3C5_MS_R01_00_BillingStatementNotification.dtd**.  

    > [!NOTE]
    >  Esta convención de nomenclatura para el espacio de nombres de destino es necesaria para BTARN. Si usa otra convención de espacio de nombres, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no procesará los documentos PIP para la validación de esquema.  
    > 
    > [!NOTE]
    >  El nombre del archivo DTD en la propiedad de espacio de nombres de destino incluye el número de versión del PIP. Esto le permite usar varias versiones del mismo código PIP.  

29. En la ventana Propiedades, desplácese hasta **importaciones**. Haga clic en el botón de puntos suspensivos (...) junto a **importaciones**y, a continuación, haga clic en **agregar**.  

30. En el **selector de tipos de BizTalk** cuadro de diálogo, expanda \< *nombre del proyecto*\>, expanda **referencias**, expanda  **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expanda **esquemas**, seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**, haga clic en **Aceptar** y, a continuación, haga clic en **Aceptar** nuevo.  

31. Haga clic con el botón derecho en el nombre del proyecto y haga clic en **Implementar**.  

32. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

33. En la consola de administración de BizTalk, expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)** y, a continuación, expanda **Hosts**. En **Host**, haga clic en **BizTalkServerApplication**.  

34. En el panel derecho, haga clic en el nombre del host y, a continuación, haga clic en **reiniciar**.  

    > [!NOTE]
    >  Después de extender los Rnpip con un PIP recién importado, debe crear la configuración correcta de PIP y un acuerdo con esa PIP, en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.  

## <a name="see-also"></a>Vea también  
 [Incorporación de un nuevo proceso de interfaz de socio](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)   
 [Trabajar con PIP](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [Modificación de un PIP existente en RNPIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)