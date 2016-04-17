### 所有操作所需权限

上传：>="编辑"

该权限指，除根目录外，其他目录的上传文件权限

新建目录：>="编辑"

该权限指，除根目录外，其他目录的新建目录权限

自定义视图：>="编辑"

该权限指，除根目录外，其他目录的新建自定义视图权限

自定义内容：>="编辑"

该权限指，除根目录外，其他目录的新建自定义内容权限

重命名：>="编辑"

该权限指，除根目录外，其他目录和文件的重命名权限

注：尽可能单选操作，如果多选，系统目前只识别按上下顺序选中的第一个资源

移动：>="编辑"

该操作权限指，除根目录外，其他目录和文件的移动权限

注：可多选。但在操作中需注意，目前必须同时具有待移动资源的"管理"权限，以及目标目录的"编辑"权限，方可进行一次移动操作。上述权限有任一不满足的情况，系统都将提示权限不足。

例如：目录A包含子目录B,要将目录B移动到目录C时,则需要用户同时具有目录B的管理权限，以及目录C的"编辑"权限，才可以完成。
共享：="管理"

该权限指，除根目录外，所有目录和文件的共享权限.

下载：>="下载"

该权限指，除根目录外，文件的下载权限

删除：="管理"

该权限指，除根目录外，所有目录和文件的删除权限

注：根目录，目前系统默认所有用户对根目录拥有"编辑"权限。即所有用户默认在可以在根目录下进行"上传、新增、重命名、下载"操作，只有用户所登陆网盘的默认权限大于根目录默认权限，或者用户拥有待操作资源的权限大于"编辑"权限时，用户才可以在根目录下进行其他操作。

网盘权限解释

目前对网盘某一资源授权时，如果它有子资源的话，系统默认会对被授权资源以及它所包含的子资源授予相同的权限。如：目录A包含子目录b和文件1,对目录A进行授权时，系统会自动将子目录b、文件1授予和目录A相同的权限。

实际使用会有以下情况：

如：目录A包含子目录b和文件1，用户拥有目录A的编辑权限，但该用户又被单独授予了子目录b的管理权限，此时用户对子目录b的权限大于父目录A的权限，这样用户要将目录b移动到目录C时，只要具有目录C的"编辑"权限，即可将目录b从目录A中移动到目录C，也就是说在这种情况下，用户可以移动子目录b，但不能移动父目录A。

注：我们仍建议用户现阶段整体对父目录授权。
如：目录A是一个空目录，目录A的创建者(用户1)把目录A的编辑权限授给用户2。这种情况下，用户2在目录A中所创建的所有资源，同时可以被用户2和用户1管理，也就是说，用户1可以删除用户2在目录A中创建的资源。所以，目前建议资源创建者对父目录授权后，如无特殊情况，暂时不参与已授权目录的管理，降低资源管理的不一致性，有使用问题时可以和我们沟通。

注：网盘权限由于具体到了文件，还涉及父子目录，较为复杂，不同情况对权限的需求也有变化，还涉及到前后端校验的一致性。所以在目前保证满足用户基本使用功能的前提下，做到有一定约束即可。