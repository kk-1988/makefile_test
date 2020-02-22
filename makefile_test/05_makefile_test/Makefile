#缺陷：还不完善不支持子目录下的某个文件
#-Wp,-MD 自动把相关索引文件信息导入到.d后缀的文件中
#$@就是名字是一一对应的

objs:= main.o sub.o

test: $(objs)
	gcc -o test main.o sub.o

#需要判断是否存在依赖文件
dep_files := $(foreach f, $(objs), .$(f).d)
#wildcard 判断相关文件是否存在
dep_files := $(wildcard $(dep_files))

#当不为空时，则包含相关依赖文件
ifneq ($(dep_files),)
    include $(dep_files)
endif

%.o:%.c
	gcc -Wp,-MD,.$@.d -c -o $@ $<

clean:
	rm *.o test

distclean:
	rm $(dep_files) *.o test
