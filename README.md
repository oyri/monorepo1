# monorepo
Testing av monorepo frå fleire micro-service-repos med utongspunkt i https://medium.com/@chris_72272/keeping-git-history-when-converting-multiple-repos-into-a-monorepo-97641744d928.


#app1
   cd ../app1

    mkdir -p app1
    git mv -k * app1
    git mv -k .* app1
    git commit -m "flytte alle filer inn i app1 mappe"
    
#app2
    cd ../app2
    mkdir -p app2
    git mv -k * app2
    git mv -k .* app2
    git commit -m "flytte alle filer inn i app2 mappe"

  # monorepo
  cd ..
  git clone git@github.com:oyri/monorepo.git
   cd monorepo
   mkdir -p app1
   mkdir -p app2
   

    git remote add -f app1 ../app1
    git remote add -f app2 ../app2

    git merge app1/main --allow-unrelated-histories
    merge app2/main --allow-unrelated-histories
  git push
