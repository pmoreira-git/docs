---

copyright:
  years: 2016
lastupdated:  "2016-10-14"
---

#	使用 Professional Per Capacity 套餐
{: #using_mobilefoundation_p4}

<!--Last updated: 12 September 2016
{: .last-updated} -->

利用 Professional Per Capacity 套餐，用户可以创建使用多个移动操作系统的任意多个移动应用程序。
创建 {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity 服务实例后，请阅读以下步骤以开始使用该服务。

## 先决条件
{: #prerequisites_p4}

配置 {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity 服务实例之前，请考虑以下问题。
* 仅 {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional（支持 OLTP）{{site.data.keyword.Bluemix_notm}} 套餐支持 {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity。

* 您应该拥有对 {{site.data.keyword.dashdbshort_notm}} 服务实例凭证的访问权，才能配置 {{site.data.keyword.mobilefoundation_short}} 服务实例的设置。

**注**：{{site.data.keyword.dashdbshort_notm}} 服务实例可以存在于您的 {{site.data.keyword.Bluemix_notm}} `组织`或您有权访问的任何其他`组织`内的任何`空间`中。请确保您有权访问 {{site.data.keyword.dashdbshort_notm}} 服务实例所在的`空间`。


## 添加数据库连接
{: #configure_dashdb_p4}

###  首要步骤
{: #firststeps_p4}

创建 {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity 服务实例后，请按照下面的过程来开始使用该服务。

### 设置与 {{site.data.keyword.dashdbshort_notm}} 服务实例的连接
{: #connect_dashdb_p4}

创建 {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity 服务实例后，您会看到*概述*页面，您需要在该页面中指定 {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional 服务实例的连接信息。

1. 选择 {{site.data.keyword.dashdbshort_notm}} 服务实例所在的 {{site.data.keyword.Bluemix_notm}} `组织`。

+ 从所选`组织`中可用的空间列表中选择具有 {{site.data.keyword.dashdbshort_notm}} 服务实例的 {{site.data.keyword.Bluemix_notm}} `空间`。

**注：**如果未看到 {{site.data.keyword.dashdbshort_notm}} 服务实例所在的`组织`和`空间`列表，请检查您是否是该`组织`和`空间`的成员。

+ 选择 {{site.data.keyword.dashdbshort_notm}} `服务名称`和`凭证`以连接到现有 {{site.data.keyword.dashdbshort_notm}} 服务实例。

+  测试与指定 {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional 服务实例的连接。

+  单击**添加**。此操作可在配置的 {{site.data.keyword.dashdbshort_notm}} 数据库服务实例中创建需要的表。

**注**：您无法更改配置为由 {{site.data.keyword.mobilefoundation_short}} 服务实例使用的 {{site.data.keyword.dashdbshort_notm}} 服务实例。但是，您可以在多个 {{site.data.keyword.mobilefoundation_short}} 服务实例上使用同一 {{site.data.keyword.dashdbshort_notm}} 服务实例，因为每个 {{site.data.keyword.mobilefoundation_short}} 服务实例都将在所选 {{site.data.keyword.dashdbshort_notm}} 服务实例中创建自己的模式。

* 几秒钟后，可以访问“`概述`”页面，其中为您提供教程和视频，可帮助您开始使用 {{site.data.keyword.mobilefoundation_short}} 服务。

## 启动 {{site.data.keyword.mobilefirst}} 服务器
{: #start_mobilefoundation_p4}

* 要使用缺省设置启动 {{site.data.keyword.mfserver_short_notm}}，请单击**启动基本服务器**。

* 此选择将为 {{site.data.keyword.mfserver_long_notm}} 供应以下设置：
    -  2 个节点，每个 1GB 内存。此大小适合用于开发、中等测试活动和小规模生产工作负载。

    -	自动为您生成 `username` 和 `password`。服务器启动并运行时，您可以对其进行访问。

供应服务器的过程启动。此过程会花费大约 10 分钟，并且消息窗口会指示此操作的进度。完成后，会显示仪表板，在其中您可以看到：

  -	正在运行的服务器的状态（状态和大小）。

  -	为您创建了服务器路径。在您的移动应用程序中使用此路径可连接到 {{site.data.keyword.mfserver_short_notm}}。

  -	用于访问 {{site.data.keyword.mfp_oc_short_notm}} 的个人 `username` 和 `password`。`password` 会隐藏。单击**显示密码**图标以使其可见。

*	单击**启动控制台**以打开 {{site.data.keyword.mfp_oc_short_notm}}。


<!--This console runs inside the container.--> 通过控制台，您可以管理移动应用程序、适配器和移动设备，还可以使用服务器作为移动后端以及发送推送通知等。



##  添加移动分析服务器
{: #adding_analytics_server_p4}

 现在，您可以将移动分析服务器添加到 {{site.data.keyword.mobilefoundation_short}} 服务实例来监视 {{site.data.keyword.mobilefirst}} 服务器上的移动应用程序。

 Professional 套餐会在容器组中创建移动分析服务器，用户可以通过选择容器组中容器节点的数量来定制配置。

 用户还可以将卷连接到容器来持久存储数据。卷一经选择，无法更改。用户可用的缺省文件共享空间为 20 GB。如果用户需要其他存储空间来持久存储分析数据，那么必须再另外购买文件共享，然后使用此文件共享来创建卷。之后部署分析服务器时，可以选择此新卷。

 有关将卷添加到 {{site.data.keyword.containerlong}} 的更多信息，请参阅[使用 {{site.data.keyword.Bluemix_notm}}“仪表板”在卷中存储持久数据](https://new-console.ng.bluemix.net/docs/containers/container_volumes_ui.html){: new_window}。

* 单击**添加分析**，将移动分析服务器添加到 {{site.data.keyword.mobilefoundation_short}} 服务实例。

* 您可以选择移动分析服务器配置，支持的分析服务器最低配置为 2 个节点，每个 1GB 内存。可以选择的分析服务器最高配置为 32 个节点，每个 16GB 内存。 

供应过程启动。此过程会花费大约 10 分钟，并且消息窗口会指示此操作的进度。  

* 从 {{site.data.keyword.mfp_oc_short_notm}} 启动 MobileFirst Analytics Console。

* 在 {{site.data.keyword.mfserver_short_notm}} 与移动分析服务器之间启用单点登录。为移动分析服务器配置与 {{site.data.keyword.mfserver_short_notm}} 服务器相同的 LTPA 密钥和用户凭证。您可以像登录 {{site.data.keyword.mfp_oc_short_notm}} 一样，使用相同的 `username` 和 `password` 登录到“移动分析”控制台。

有关 MobileFirst Analytics 的更多信息，可以参阅 [MobileFirst Foundation Operational Analytics](https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/8.0/analytics/)。

**注：**删除 {{site.data.keyword.mobilefoundation_short}} 服务实例或尝试重新创建 {{site.data.keyword.mfserver_short_notm}} 时，会除去移动分析服务器。

## 重新创建 {{site.data.keyword.mobilefirst}} 服务器
{: #recreate_mobilefoundation_p4}

*	单击**重新创建**以重新创建服务器。

* 此操作将停止现有服务器并删除数据。将会使用更新的版本（如果可用）来创建新的服务器实例。此操作会花费几分钟才能完成。

**注**：先前服务器实例中的所有数据（包括有关应用程序和适配器的信息）会持久存储在配置的 {{site.data.keyword.dashdbshort_notm}} 服务实例中，在重新创建服务器时会使用这些数据。

##	设置高级配置
{: #using_mfs_advanced_p4}

使用“`概述`”页面中的**使用高级配置启动服务器**，可使用高级或定制设置创建服务器。还可以通过单击**配置**选项卡更新服务器设置，以定制服务器配置。{{site.data.keyword.mobilefoundation_short}} 为您提供对某些高级设置的访问权。

*	在**拓扑**选项卡中，可以选择服务器大小以及所需的服务器实例数。缺省 1 GB 服务器足够开发和轻量测试使用。
  - 根据您的需要，选择正确的服务器大小。

  - **节点**显示已创建的节点数。

      - 配置此处列出的节点数可创建 {{site.data.keyword.mobilefirst}} 服务器机群。支持的最低配置为 2 个节点，每个 1GB 内存；支持的最高配置为 32 个节点，每个 16GB 内存。 

请参阅 [{{site.data.keyword.mobilefoundation_long}} 文档](https://www.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html){: new_window}，以获取更多详细信息。
