---
title: SchemaValidator | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9e3921b8bf83e3e7e775efef77a029bfda2e7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="schemavalidator"></a>SchemaValidator
Utilice la utilidad SchemaValidator para solucionar problemas relacionados con una instancia de mensaje. Si recibe un mensaje que se produce un error de validación, puede ejecutar la utilidad SchemaValidator para determinar el origen del error.  
  
 Use esta utilidad si usa un ensamblado que incluye un archivo .dll de esquema y no tiene un archivo de esquema XSD. La utilidad SchemaValidator le permite validar usando el archivo .dll de esquemas.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator  
  
## <a name="building-and-running-schemavalidator"></a>Compilar y ejecutar SchemaValidator  
  
#### <a name="to-build-the-schemavalidator-utility"></a>Para generar la utilidad SchemaValidator  
  
1.  Abra un símbolo del sistema.  
  
2.  Mover a \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.  
  
3.  En el símbolo del sistema, escriba **sn -k SchemaValidator.snk**, y, a continuación, presione ENTRAR.  
  
4.  Inicie **Microsoft Visual Studio 2012**.  
  
5.  En el **archivo** menú, elija **abiertos**y, a continuación, haga clic en **Abrir solución**.  
  
6.  Mover a \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator, seleccione **SchemaValidator.sln** y, a continuación, haga clic en **abiertos**.  
  
7.  En el Explorador de soluciones, haga clic en **SchemaValidator**y, a continuación, haga clic en **propiedades**.  
  
8.  En la página **Propiedad de MessageInspector**  , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** . Seleccione **SchemaValidator.snk** en **elegir un archivo de clave de nombre seguro**.  
  
9. Haga clic en **SchemaValidator.cs**.  
  
10. Escriba la ruta de acceso de la instancia de mensaje adecuado en la siguiente línea existente de código en `Main`:  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. Reemplace la línea siguiente existente de código en `Main` con una referencia al ensamblado Rnpip y, a continuación, seleccione el esquema apropiado:  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. Haga clic en **SchemaValidator**y, a continuación, haga clic en **generar**.  
  
13. Modificar la instancia de mensaje al que desea probar mediante la eliminación de la \< \!DOCTYPE... \> etiqueta Especifica el archivo DTD desde el encabezado de la instancia XML.  
  
14. En el nodo raíz de la instancia de mensaje, agregue un espacio de nombres XML del esquema que se validarán ante.  
  
    > [!NOTE]
    >  Para obtener un ejemplo de un esquema listo para ser validado por la utilidad SchemaValidator, vea Sample3A4.xml en \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.  
  
15. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **SchemaValidator.cs**y, a continuación, presione CTRL y F5 para ejecutar la utilidad.  
  
## <a name="remarks"></a>Comentarios  
 Dado que el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye el código de SchemaValidator, puede agregar lógica a la utilidad. Por ejemplo, puede realizar una utilidad de línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)