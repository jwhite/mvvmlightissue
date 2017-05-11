# mvvmlightissue
Reproduction showing issue adding mvvm light to a c++/cli dll.

We have a fairly substantial product built in part on mvvm light.  That product used C++/CLI and targetted .Net 4.0.

When converting the product to .Net 4.6 MvvmLight was updated to the latest version.

This simple solution/project reproduces the issue encountered while using the MvvmLight net45 assemblies in a C++/CLI library.

Here is the build error experienced:

warning C4691: 'System::Object': type referenced was expected in unreferenced assembly 'System.Runtime', type defined in current translation unit used instead


Here is the full build error output:

1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): warning C4691: 'System::Object': type referenced was expected in unreferenced assembly 'System.Runtime', type defined in current translation unit used instead
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ObservableObject ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ViewModelBase ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): warning C4691: 'System::Runtime::CompilerServices::CallerMemberNameAttribute': type referenced was expected in unreferenced assembly 'System.Runtime', type defined in current translation unit used instead
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ObservableObject ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ViewModelBase ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): warning C4691: 'System::Func': type referenced was expected in unreferenced assembly 'System.Runtime', type defined in current translation unit used instead
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ObservableObject ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ViewModelBase ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): warning C4691: 'System::Nullable': type referenced was expected in unreferenced assembly 'System.Runtime', type defined in current translation unit used instead
1>  d:\source\github\mvvmlightissue\library\library\ViewModel.h(6): note: This diagnostic occurred while importing type 'GalaSoft::MvvmLight::ViewModelBase ' from assembly 'GalaSoft.MvvmLight, Version=5.3.0.19026, Culture=neutral, PublicKeyToken=e7570ab207bcb616'.


