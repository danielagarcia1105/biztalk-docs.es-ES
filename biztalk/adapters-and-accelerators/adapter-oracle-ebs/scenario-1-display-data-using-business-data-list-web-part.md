---
title: 'Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1add974ca3ad0b80b7838b120920f4de47f1650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217436"
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a>Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos
Usaremos el **lista de datos económicos** elemento Web para la **buscador** instancia de método. Este elemento Web le permite especificar una expresión de búsqueda para recuperar una lista de empleados de Oracle E-Business Suite. Para este tutorial, esto se denomina el elemento Web de los empleados de presentación. Esta sección proporciona instrucciones para crear este elemento Web. Para obtener más información acerca de cómo crear elementos Web, vea "Personalizar listas de datos de negocio, elementos Web y sitios" en [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).  
  
 Debe crear una página de elementos Web antes de agregar los elementos Web.  
  
## <a name="creating-a-web-part-page"></a>Crear una página de elementos Web  
 Esta sección proporciona instrucciones para crear una página de elementos Web.  
  
###  <a name="WebPart"></a>Para crear una página de elementos Web  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
     ![Menú para crear un elemento web](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  En la página Crear, en el **páginas Web** sección, haga clic en **página de elementos Web**.  
  
5.  En la página nuevo elemento Web, haga lo siguiente:  
  
    1.  En el **nombre** , escriba un nombre para la página. Para este tutorial, escriba el nombre como **MS_SAMPLE_EMPLOYEE**.  
  
    2.  Seleccione el **sobrescribir si ya existe el archivo** casilla de verificación si desea sobrescribir páginas anteriores con el mismo nombre que la página nueva que cree.  
  
    3.  En el **diseño** sección, desde el **elegir una plantilla de diseño** , seleccione un diseño para la página de elementos Web. Para este tutorial, seleccione **página completa, Vertical**.  
  
    4.  En el **ubicación de almacenamiento** sección, en la **biblioteca de documentos** lista, haga clic en **plantillas de formulario**.  
  
    5.  Haga clic en **Crear**. La siguiente ilustración muestra la página de elementos Web después de crearlo.  
  
         ![La nueva página de elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")  
  
    6.  Ahora debe agregar los elementos Web a esta página.  
  
## <a name="adding-a-business-data-list-web-part"></a>Agregar un elemento Web de lista de datos de negocio  
 Ahora debe agregar un elemento Web de lista de datos de negocio a la página de elementos Web. Con este elemento Web recuperará una lista de los registros de empleados de la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite que coincide con una expresión de búsqueda. Este elemento Web corresponde a la **buscador** instancia de método (*Finder_Instance*) que creó en el Editor de definición de catálogo de datos de Business.  
  
#### <a name="to-add-a-business-data-list-web-part"></a>Para agregar un elemento Web de lista de datos de negocio  
  
1.  En la página MS_SAMPLE_EMPLOYEE, haga clic en **agregar un elemento Web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo, en la **datos económicos** sección, seleccione la **lista de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
     ![Opciones para crear un elemento Web de datos empresariales](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  En la parte de Web de recién agregado Business datos de lista, haga clic en el **abrir el panel de herramientas** vínculo.  
  
     ![Abra el panel de herramientas para el elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  El panel de herramientas de la lista de datos económicos se abre en el panel derecho. En el **lista de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Panel de herramientas de lista de datos de negocio](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")  
  
5.  En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **MS_SAMPLE_EMPLOYEE_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
     ![Seleccione la instancia de aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")  
  
6.  Expanda el **apariencia** nodo y en el **título** , escriba un título para el elemento Web. Para este elemento Web, escriba **lista de empleados**.  
  
7.  En el panel de herramientas de la lista de datos económicos, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**. El elemento Web de lista de datos de negocio ahora el siguiente aspecto:  
  
     ![Elemento Web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")  
  
8.  El elemento Web se enumeran los campos que se devuelven mediante la ejecución de la operación de selección en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)   
 [Escenario 2: Realizar búsquedas mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)