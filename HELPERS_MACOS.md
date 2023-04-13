
# Tag Modules
```
tag_modules () {
	if [ "$1" = "master" ] || [ "$1" = "main" ] ; then
		echo  " '\e[0;31m' you can't create a tag with this name"
	else
		if [ $(git tag -l "$1") ]; then
		echo "this tag already exists"
		echo "are you sure to override it ? [y/n]"
		read answer

		if [ "$answer" != "${answer#[Yy]}" ]; then
    			echo delete old tag
        		git tag -d "$1"
        		git push --delete origin "$1"
        		git tag "$1"
        		git push -f origin "$1"
        		git submodule foreach '

   			if [ $(git tag -l '"$1"') ]; then
        			echo tag already exists
        		echo delete old tag
        			git tag -d '"$1"'
        			git tag '"$1"'
      				git push -f origin '"$1"'
    			else
        			echo create a tag
        			git tag '"$1"'
        			git push -f origin '"$1"'
    			fi
			'
			else
    				echo ok..
			fi
      			echo end process 
   		else
       			echo create a tag
        		git tag "$1"
        		git push -f origin "$1"
			git submodule foreach '
	
   				if [ $(git tag -l '"$1"') ]; then
        				echo tag already exists
        				echo delete old tag
        				git tag -d '"$1"'
        				git tag '"$1"'
      					git push -f origin '"$1"'
    				else
        				echo create a tag
        				git tag '"$1"'
        				git push -f origin '"$1"'
    				fi
			'
        		echo end process 
    		fi
	fi
}
```

# Fetch from Tags
```
get_from_tag () {
	git checkout "$1"
        git submodule foreach 'git checkout '"$1"''
}
```