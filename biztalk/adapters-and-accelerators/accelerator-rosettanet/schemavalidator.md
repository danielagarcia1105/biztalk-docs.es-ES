---
title: SchemaValidator | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf31f22cc2b79e6dded22e04500655110f242ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973877"
---
# <a name="schemavalidator"></a>SchemaValidator
Use la utilidad SchemaValidator para solucionar problemas relacionados con una instancia de mensaje. Si recibe un mensaje que se produce un error de validación, puede ejecutar la utilidad SchemaValidator para determinar el origen del error.  
  
 Use esta utilidad si usa un ensamblado que incluye un archivo .dll de esquema y no tiene un archivo de esquema XSD. La utilidad SchemaValidator le permite validar con el archivo .dll de esquema.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator  
  
## <a name="building-and-running-schemavalidator"></a>Compilar y ejecutar SchemaValidator  
  
#### <a name="to-build-the-schemavalidator-utility"></a>Para generar la utilidad SchemaValidator  
  
1. Abra un símbolo del sistema.  
  
2. Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.  
  
3. En el símbolo del sistema, escriba **sn -k SchemaValidator.snk**, y, a continuación, presione ENTRAR.  
  
4. Inicie **Microsoft Visual Studio 2012**.  
  
5. En el **archivo** menú, elija **abierto**y, a continuación, haga clic en **Abrir solución**.  
  
6. Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator, seleccione  **SchemaValidator.sln**y, a continuación, haga clic en **abierto**.  
  
7. En el Explorador de soluciones, haga clic en **SchemaValidator**y, a continuación, haga clic en **propiedades**.  
  
8. En la página **Propiedad de MessageInspector**  , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** . Seleccione **SchemaValidator.snk** en **elegir un archivo de clave de nombre seguro**.  
  
9. Haga clic en **SchemaValidator.cs**.  
  
10. Escriba la ruta de acceso de la instancia de mensaje adecuado en la siguiente línea existente de código en `Main`:  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. Reemplace la siguiente línea existente de código en `Main` con una referencia al ensamblado Rnpip y a continuación, seleccione el esquema apropiado:  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. Haga clic en **SchemaValidator**y, a continuación, haga clic en **compilar**.  
  
13. Modificar la instancia de mensaje al que desea probar quitando el \< \!DOCTYPE... \> etiqueta especificando el archivo DTD desde el encabezado de la instancia XML.  
  
14. En el nodo raíz de la instancia de mensaje, agregue un espacio de nombres del esquema que se validará en XML.  
  
    > [!NOTE]
    >  Para obtener un ejemplo de un esquema de listo para su validación por la utilidad SchemaValidator, consulte Sample3A4.xml en \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.  
  
15. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **SchemaValidator.cs**y, a continuación, presione CTRL y presione F5 para ejecutar la utilidad.  
  
## <a name="remarks"></a>Notas  
 Dado que el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye el código SchemaValidator, puede agregar lógica a la utilidad. Por ejemplo, puede hacer una utilidad de línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
