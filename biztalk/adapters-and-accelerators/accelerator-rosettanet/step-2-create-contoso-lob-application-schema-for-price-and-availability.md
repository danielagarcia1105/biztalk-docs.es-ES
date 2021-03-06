---
title: 'Paso 2: Crear los esquemas de aplicación de LOB de Contoso para el precio y disponibilidad del proyecto mediante el Editor de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999333"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a>Paso 2: Creación de los esquemas de aplicación de LOB de Contoso para el proyecto precio y disponibilidad mediante el Editor de BizTalk
En este paso, se genera el esquema se utiliza para consultar el sistema de ERP de Contoso para el precio y disponibilidad de un producto determinado. Generar este esquema mediante el uso del adaptador de SQL de Microsoft® para BizTalk Server.  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a>Para actualizar el código SQL el procedimiento almacenado para generar esquemas  

1.  Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  

2.  En Microsoft SQL Server Management Studio, expanda **bases de datos**, expanda **Contoso**, expanda **programación**y, a continuación, expanda **procedimientos almacenados** .  

3.  Haga clic en **dbo. SP_GetInventoryForProductID**y, a continuación, haga clic en **modificar**.  

4.  En la ventana de consulta, insertar una coma, un espacio y, a continuación, "xmldata" inmediatamente después de "for xml auto". La línea de código debería ser la siguiente:  

    ```  
    for xml auto, xmldata  
    ```  

5.  Haga clic en **Execute** para guardar los cambios en el procedimiento almacenado.  

    > [!NOTE]
    >  Deje que Microsoft SQL Server Management Studio abierta para el siguiente procedimiento.  

### <a name="to-create-the-contoso-price-and-availability-schema"></a>Para crear el esquema Contoso Price y disponibilidad  

1. Abra la solución de Contoso en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  

2. En el Explorador de soluciones, haga clic en el **ContosoPriceAndAvailability** , seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

3. En el cuadro de diálogo Agregar fluyan generados con **agregar metadatos de adaptador** seleccionado en el panel izquierdo, haga clic en **agregar metadatos de adaptador** en el panel derecho y, a continuación, haga clic en **agregar**.  

4. En el **Asistente para agregar adaptador** página, seleccione **SQL** en la lista de adaptadores registrados y, a continuación, haga clic en **siguiente**.  

5. En el **información de la base de datos** página, haga clic en **establecer**.  

6. En el cuadro de diálogo Propiedades de vínculo de datos, en el cuadro **Seleccione o escriba un nombre de servidor** , escriba **localhost**. Seleccionar **Usar seguridad integrada de Windows**. Para **seleccione la base de datos en el servidor**, seleccione el **Contoso** base de datos de la lista de bases de datos. Haga clic en **Aceptar**.  

7. En el **información de la base de datos** página, haga clic en **siguiente**.  

8. En el **información del esquema** página, realice lo siguiente:  


   |                Use                 |              Para              |
   |-----------------------------------------|--------------------------------------|
   |          **Espacio de nombres de destino**           | Tipo **<http://Contoso.com/Price>**. |
   |        **Seleccione el tipo de puerto**         |        Seleccione **puerto de envío**.         |
   | **Nombre de elemento raíz de documento de solicitud**  |      Tipo **rootPriceRequest**.      |
   | **Nombre de elemento raíz de documento de respuesta** |     Tipo **rootPriceResponse**.      |


9. Haga clic en **Siguiente**.  

10. En el **información de tipo de instrucción** página, seleccione **Stored Procedure**y, a continuación, haga clic en **siguiente**.  

11. En el **instrucción** página, para  **\<seleccionar un procedimiento almacenado\>**, seleccione **SP_GetInventoryForProductID** desde el lista desplegable. Haga clic en **generar**y, a continuación, haga clic en **siguiente**.  

12. En el **completando el Asistente para generación de esquema de transporte SQL** página, haga clic en **finalizar** para importar el esquema en el proyecto de ContosoPriceAndAvailability BizTalk.  

13. En el Explorador de soluciones, haga clic en el esquema generado (SQLService_Price.xsd), haga clic en **cambiar el nombre de**y el tipo **ContosoPriceAndAvailability.xsd** como el nuevo nombre para el esquema. Haga clic en **Entrar**.  

14. En la ventana Propiedades para el esquema ContosoPriceAndAvailability, establezca el **nombre de tipo** propiedad **ContosoPriceSchema**.  

15. De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] crea una orquestación de BizTalk denominada **BizTalk Orchestration.odx**. Haga clic en esta orquestación y, a continuación, haga clic en **eliminar** porque no necesita esta orquestación. En la ventana emergente que indica que se eliminará permanentemente la orquestación, haga clic en **Aceptar**.  

16. En Microsoft SQL Server Management Studio, quite el `xmldata` predicado y el punto y coma de los `SP_GetInventoryForProductID` el procedimiento almacenado que agregó en el paso anterior y, a continuación, haga clic en **Execute**.  

## <a name="see-also"></a>Vea también  
 [Paso 3: Creación de los mapas de aplicación de LOB de Contoso para el proyecto Precio y disponibilidad mediante el Asignador de BizTalk](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)