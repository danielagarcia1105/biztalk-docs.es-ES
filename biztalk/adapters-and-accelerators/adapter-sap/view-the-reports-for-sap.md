---
title: Ver los informes para SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8643ef37e3fe4aec77cd9d218a171d37c2c24852
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974613"
---
# <a name="view-the-reports-for-sap"></a>Ver los informes para SAP
Después de haber creado el informe, puede ver mediante Visual Studio o bien hospedar en el servidor de informes en Internet Information Services (IIS) y el acceso a través de la red. Este tema proporciona instrucciones sobre cómo ver los informes tanto en Visual Studio y el uso de IIS.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de realizar los procedimientos proporcionados en este tema, debe ha generado un informe como se describe en [usar el proveedor de datos para SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md).  
  
### <a name="to-view-the-reports-in-visual-studio"></a>Para ver los informes en Visual Studio  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.  
  
2. En el cuadro de diálogo páginas de propiedad de informe, haga clic en **Configuration Manager**y desactive la casilla situada bajo la **implementar** columna. Haga clic en **Cerrar**.  
  
3. En el cuadro de diálogo de páginas de propiedad de informe para el **StartItem** propiedad, seleccione el nombre del informe y, a continuación, haga clic en **Aceptar**.  
  
    ![Especificar propiedades para el proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")  
  
4. Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **compilar**.  
  
5. Presione `F5` para ejecutar el proyecto para generar el informe.  
  
   > [!IMPORTANT]
   >  En [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], puede ver el informe, haga clic en el **Preview** ficha. En tal caso, los cuadros de diálogo subsiguientes se abrirá dentro de la pestaña de vista previa.  
  
6. Abre un cuadro de diálogo con el mismo nombre que ha especificado para el informe. Al crear el origen de datos, si eligió el **pedir credenciales** opción, escriba el nombre de usuario y la contraseña para el sistema SAP y, a continuación, haga clic en **Ver informe**.  
  
    ![Especifique las credenciales SAP para generar un informe](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")  
  
7. Si la consulta que especificó al crear el proyecto de servidor de informes requiere un parámetro, debe escribir el valor del parámetro. Por ejemplo, para la consulta especifica en el [usar el proveedor de datos para SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) tema, es preciso especificar un valor para el parámetro.  
  
    Especifique el valor del parámetro, si es necesario y haga clic en **Ver informe**.  
  
    ![Especificar parámetros para generar un informe](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")  
  
### <a name="to-host-the-reports-on-report-server"></a>Para hospedar los informes en el servidor de informes  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.  
  
2. En el cuadro de diálogo páginas de propiedad de informe, haga clic en **Configuration Manager**y seleccione la casilla situada bajo la **implementar** columna. Haga clic en **Cerrar**.  
  
3. En el cuadro de diálogo de páginas de propiedad de informe para el **StartItem** propiedad, seleccione el nombre del informe.  
  
4. En el cuadro de diálogo de páginas de propiedad de informe para el **TargetServerURL** propiedad, especifique una dirección URL del servidor de informes y, a continuación, haga clic en **Aceptar**. Por ejemplo:  
  
   ```  
   http://localhost/reportserver  
   ```  
  
    ![Especifique la dirección URL del servidor de informes](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")  
  
5. Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **compilar**.  
  
6. Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **implementar**.  
  
7. Inicie IIS. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `inetmgr`y presione `Enter`.  
  
8. En el **Internet Information Services (IIS) Manager** complemento, expanda el nombre del equipo, **sitios Web**, expanda **sitio Web predeterminado**, haga clic en  **ReportServer**y, a continuación, haga clic en **examinar**.  
  
9. En el panel derecho, haga clic en el nombre del proyecto y, a continuación, haga clic en el nombre del informe.  
  
10. Al crear el origen de datos, si eligió el **pedir credenciales** opción, escriba el nombre de usuario y la contraseña para el sistema SAP y haga clic en **Ver informe**.  
  
11. Si la consulta que especificó al crear el proyecto de servidor de informes requiere un parámetro, debe escribir el valor del parámetro. Por ejemplo, para la consulta especifica en el [usar el proveedor de datos para SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) tema, es preciso especificar un valor para el parámetro.  
  
     Especifique el valor del parámetro, si es necesario y haga clic en **Ver informe**.  
  
     ![Especificar parámetros para generar un informe](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")  
  
    > [!TIP]
    >  También puede ver directamente desde el explorador web proporcionando la dirección URL para el informe. Una dirección URL típica para el informe `is http://localhohost/reportserver/<report_name>`.  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos para SAP con SSRS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)