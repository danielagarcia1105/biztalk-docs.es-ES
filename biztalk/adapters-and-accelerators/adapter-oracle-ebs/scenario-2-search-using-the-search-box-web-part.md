---
title: 'Escenario 2: Realizar búsquedas mediante el elemento web de cuadro de búsqueda | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218548"
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a>Escenario 2: Realizar búsquedas mediante el elemento web de cuadro de búsqueda
Se va a configurar la configuración de búsqueda en Microsoft Office SharePoint Server para configurar una aplicación de búsqueda con la que puede realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite. Más adelante, agregaremos un elemento de Web de cuadro de búsqueda para desde donde puede realizar la búsqueda.  
  
 
  
##  <a name="Define"></a>Definir el origen de contenido  
 Esta sección trata acerca de cómo definir un origen de contenido desde donde Microsoft Office SharePoint Server puede rastrear los datos. Esto consiste en asignar el contenido para el enumerador de Id. de instancia de método creado en [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).  
  
#### <a name="to-define-a-content-source"></a>Para definir un origen de contenido  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.  
  
3.  En la página principal, en la **búsqueda** sección, haga clic en **configuración de búsqueda**.  
  
4.  En la página Configurar opciones de búsqueda, en el panel izquierdo bajo **rellenando**, haga clic en **cuenta de acceso al contenido predeterminada** para especificar una cuenta para utilizarla como la cuenta predeterminada cuando se rastrea contenido.  
  
5.  En la página cuenta de acceso al contenido predeterminado, especifique las credenciales de contraseña y nombre de usuario y haga clic en **Aceptar**. Volverá a la página de administración de búsqueda.  
  
6.  En el panel izquierdo bajo **rellenando**, haga clic en **orígenes de contenido**.  
  
7.  En la página Administrar orígenes de contenido, haga clic en **nuevo origen de contenido**.  
  
8.  En la página Administrar orígenes de contenido, haga clic en **nuevo origen de contenido**.  
  
9. En la página Agregar origen de contenido:  
  
    1.  Tipo de `MS_SAMPLE_EMPLOYEE` en el **nombre** cuadro.  
  
    2.  En el **tipo de origen de contenido** área, haga clic en **datos económicos**.  
  
    3.  En el **aplicaciones** área, haga clic en **las aplicaciones seleccionadas de rastreo**y, a continuación, seleccione la **MS_SAMPLE_EMPLOYEE_Instance** casilla de verificación.  
  
    4.  En el **Iniciar rastreo completo** área, seleccione la **Iniciar rastreo completo de este origen de contenido** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
         ![Agregar origen de contenido](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")  
  
10. Volverá a la página Administrar orígenes de contenido con el nuevo origen de contenido agregado. El origen de contenido se rastreará a través de los datos en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite. Espere hasta que el rastreo se ha completado.  
  
11. En el panel izquierdo bajo **rellenando**, haga clic en **registro de rastreo**y, a continuación, compruebe el archivo de registro para asegurarse que el rastreo se realice correctamente.  
  
##  <a name="Scope"></a>Definir un ámbito para el contenido rastreado  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.  
  
3.  En la página principal, en la **búsqueda** sección, haga clic en **configuración de búsqueda**.  
  
4.  En la página Configurar opciones de búsqueda, en el panel izquierdo bajo **consulta y resultados**, haga clic en **ámbitos** para definir un ámbito para el rastreo de datos.  
  
5.  En la página Ver ámbitos, haga clic en **nuevo ámbito**.  
  
6.  En la página Crear ámbito, escriba `MS_SAMPLE_EMPLOYEE_Search` en el **título** cuadro y, a continuación, haga clic en **Aceptar**.  
  
     ![Crear un ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")  
  
7.  Volverá a la página Ver ámbitos con el nuevo ámbito agregado. En el **estado de actualización** columna para el ámbito recién agregado, haga clic en el **agregar reglas** vínculo.  
  
8.  En la página Agregar regla de ámbito:  
  
    1.  En el **tipo de regla de ámbito** área, haga clic en **origen de contenido**.  
  
    2.  En el **origen de contenido** lista, haga clic en **MS_SAMPLE_EMPLOYEE**y, a continuación, haga clic en **Aceptar**.  
  
         ![Agregar una regla de ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")  
  
9. Volverá a la página Ver ámbitos con la regla agregada para el ámbito. En el panel izquierdo, haga clic en **administración de búsqueda**.  
  
10. En la página de administración de búsqueda, busque el **ámbitos que requieren actualización** de fila y haga clic en el **Iniciar actualización ahora** vínculo.  
  
 El **estado de actualización de ámbito** fila mostrará el estado de la actualización de ámbito. Espere hasta que finalice la actualización. Una vez completada la actualización, el ámbito está listo para usarse.  
  
##  <a name="AddScope"></a>Agregar el ámbito a la lista desplegable de búsqueda  
 Después de haber creado el ámbito de búsqueda, debe agregar el ámbito a la lista desplegable de búsqueda en Microsoft Office SharePoint Server para que se puede utilizar.  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a>Para agregar el ámbito a la lista desplegable de búsqueda  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre de los servicio proveedor compartidos (SSP) que va a configurar la aplicación de búsqueda.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **configuración del sitio**.  
  
4.  En la página Configuración del sitio, en la **administración de colección de sitios** sección, haga clic en **ámbitos de búsqueda**.  
  
5.  En la página Ver ámbitos, haga clic en el **cuadro desplegable de búsqueda** vínculo.  
  
     ![Ver ámbitos](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")  
  
6.  En la página Editar grupo de presentación de ámbito:  
  
    1.  En el **ámbitos** área, seleccione la **MS_SAMPLE_EMPLOYEE_Search** casilla de verificación.  
  
    2.  En el **ámbito predeterminado** área, haga clic en **MS_SAMPLE_EMPLOYEE_Search** en el **ámbito predeterminado** lista y, a continuación, haga clic en **Aceptar**.  
  
         ![Página Editar grupo de presentación de ámbito](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")  
  
7.  Volverá a la página Ver ámbitos con el ámbito de MS_SAMPLE_EMPLOYEE_Search agregado en el grupo de presentación de la lista desplegable de búsqueda.  
  
##  <a name="SearchWebPart"></a>Agregar el elemento Web de cuadro de búsqueda  
 Para permitir a los usuarios a realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite, ahora debe crear una página de elementos Web y agregar un elemento Web de cuadro de búsqueda a él.  
  
#### <a name="to-add-the-search-box-web-part"></a>Para agregar el elemento Web de cuadro de búsqueda  
  
1.  Cree una página de elemento Web denominada **MS_SAMPLE_EMPLOYEE_Search**. Para conocer los pasos para crear una página de elementos Web, consulte [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md) en [escenario 1: mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).  
  
2.  En la página MS_SAMPLE_EMPLOYEE_Search, haga clic en **agregar un elemento Web**.  
  
3.  En el **agregar elementos Web** cuadro de diálogo, en la **búsqueda** sección, seleccione la **cuadro de búsqueda** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
     ![Agregar el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")  
  
4.  El elemento Web cuadro de búsqueda se agrega a la página MS_SAMPLE_EMPLOYEE_Search.  
  
     ![Elemento Web cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)