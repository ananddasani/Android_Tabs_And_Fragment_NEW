# Android_Tabs_And_Fragment_NEW
Controlling Tabs and Fragment Using New Class FragmentStateAdapter

This topic is a part of [My Complete Andorid Course](https://github.com/ananddasani/Android_Apps)

# Code

#### FragmentAdapter.java
```
 public class FragmentAdapter extends FragmentStateAdapter {

    private String[] titles = {"HOME", "MOVIE", "SONG"};

    public FragmentAdapter(@NonNull FragmentActivity fragmentActivity) {
        super(fragmentActivity);
    }

    @NonNull
    @Override
    public Fragment createFragment(int position) {

        switch (position){
            case 0 : return new FragmentHome();
            case 1 : return new FragmentMovie();
            case 2 : return new FragmentSong();
        }
        return new FragmentHome();
    }

    @Override
    public int getItemCount() {
        return titles.length;
    }
}
```

#### MainActivity.java
```
private String[] titles = {"HOME", "MOVIE", "SONG"};

FragmentAdapter fragmentAdapter;
TabLayout tabLayout;
ViewPager2 viewPager2;

viewPager2 = findViewById(R.id.viewPager2);
tabLayout = findViewById(R.id.tabLayout);

fragmentAdapter = new FragmentAdapter(this);

viewPager2.setAdapter(fragmentAdapter);

new TabLayoutMediator(tabLayout, viewPager2, ((tab, position) -> tab.setText(titles[position]))).attach();
```

# App Highlight

![Tabs New App1](https://user-images.githubusercontent.com/74413402/192095623-d00c6bb2-9838-46f1-9d1e-14b0150c8f92.png)
![Tabs New App2](https://user-images.githubusercontent.com/74413402/192095624-a14fd248-41ea-4cef-a760-2f7fb29e07c5.png)
![Tabs New App3](https://user-images.githubusercontent.com/74413402/192095625-41158266-780a-47e1-ac93-829627feea56.png)
![Tabs New Code](https://user-images.githubusercontent.com/74413402/192095630-9f253674-3640-4afc-9974-67d2dabb0338.png)

