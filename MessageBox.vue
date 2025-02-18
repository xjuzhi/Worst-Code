<!--
author: xjuzhi
createDate: 2024年12月06日18时16分21秒
item: video
description: 本文件使用Vue3+less, 多层弹窗嵌套模板
-->
<script setup>
import router from "@/router";
import axios from 'axios'


// 第一个消息框函数
const messagebox1 = () => {
  return ElMessageBox.confirm('能不能喜欢我？', '能不能喜欢我', {
    confirmButtonText: '能',
    cancelButtonText: '不能'
  });
};

// 第二个消息框函数（对应第一个消息框选择“能”后的情况）
const messagebox2 = () => {
  return ElMessageBox.confirm('真的能喜欢我吗？', '真的能喜欢我吗？', {
    confirmButtonText: '能',
    cancelButtonText: '不能'
  });
};

// 第三个消息框函数（对应第一个消息框选择“不能”后的情况）
const messagebox3 = () => {
  return ElMessageBox.confirm('真的不能喜欢我吗？', '真的不能喜欢我吗？', {
    confirmButtonText: '能',
    cancelButtonText: '不能'
  });
};

// 第四个消息框函数（对应第二个消息框选择“能”后的情况）
const messagebox4 = () => {
  return ElMessageBox.confirm('真是真的吗？', '真是真的吗？', {
    confirmButtonText: '真的',
    cancelButtonText: '假的'
  });
};

// 第五个消息框函数（对应第二个消息框选择“不能”后的情况）
const messagebox5 = () => {
  return ElMessageBox.confirm('点错了对不对？', '点错了对不对？', {
    confirmButtonText: '点错了',
    cancelButtonText: '没点错'
  });
};
// 第六个消息框函数（对应第四个消息框选择“真的”后的情况）
const messagebox6 = () => {
  return ElMessageBox.confirm('好耶，我有个想法能说吗？', '真的吗，我有个想法能说吗？', {
    confirmButtonText: '可以',
    cancelButtonText: '不可以'
  });
};
// 第七个消息框函数（对应第四个消息框选择“假的”后的情况）
const messagebox7 = () => {
  // console.log('我调用了7号函数')
  return messagebox3()
};
// 第八个消息框函数（对应第六个消息框选择“可以”后的情况）
const messagebox8 = () => {
  return ElMessageBox.confirm('我能去见你吗？', '我能去见你吗？', {
    confirmButtonText: '可以',
    cancelButtonText: '不可以'
  });
};
// 第九个消息框函数（对应第六个消息框选择“不可以”后的情况）
const messagebox9 = () => {
  return ElMessageBox.alert('好吧', '好吧', {
   confirmButtonText: '确定'
  }).then(() => {
    jumpToPage()
    // 调用后端接口发送邮件（假设后端有对应的 /send-email 接口用于发送邮件，根据实际情况调整）
    return axios.post('/send-email');
  }).catch((error) => {
    console.log('邮件发送失败，错误信息:', error);
  });
};
// 第十个消息框函数（对应第八个消息框选择“可以”后的情况）
const messagebox10 = () => {
  return ElMessageBox.alert('我这就去买票', '我这就去买票', {
   confirmButtonText: '确定'
  }).then(() => {
    // router.push('/')
    // 调用后端接口发送邮件（假设后端有对应的 /send-email 接口用于发送邮件，根据实际情况调整）
    return axios.post('/send-email');
  }).catch((error) => {
    console.log('邮件发送失败，错误信息:', error);
  });
};

// 第十一个消息框函数（对应第八个消息框选择“不可以”后的情况）
const messagebox11 = () => {
  // console.log('我调用了11号函数')
  return messagebox9()
};

// 第十二个消息框函数（对应第三个消息框选择“能”后的情况）
const messagebox12 = () => {
  // console.log('我调用了12号函数')
  return messagebox2()
};

// 第十三个消息框函数（对应第三个消息框选择“不能”后的情况）
const messagebox13 = () => {
  return ElMessageBox.confirm('真的不能吗？', '真的不能吗？', {
    confirmButtonText: '能',
    cancelButtonText: '不能'
  });
};

// 第十四个消息框函数（对应第十三个消息框选择“能”后的情况）
const messagebox14 = () => {
  // console.log('我调用了14号函数')
  return messagebox2()
};

// 第十五个消息框函数（对应第十三个消息框选择“不能”后的情况）
const messagebox15 = () => {
  return ElMessageBox.confirm('真不能吗，姐姐？', '真不能吗，姐姐？', {
    confirmButtonText: '能',
    cancelButtonText: '不能'
  });
};

// 第十六个消息框函数（对应第十五个消息框选择“能”后的情况）
const messagebox16 = () => {
  // console.log('我调用了16号函数')
  return messagebox2()
};

// 第十七个消息框函数（对应第十五个消息框选择“不能”后的情况）
const messagebox17 = () => {
  return ElMessageBox.alert('好吧，等过段时间我再问', '好吧，等过段时间我再问', {
  confirmButtonText: '确定'
});
};

// 第十八个消息框函数(对应第五个消息框选择“点错了”后的情况)
const messagebox18 = () => {
  // console.log('我调用了18号函数')
  return messagebox4()
};

// 第十九个消息框函数（对应第十七个消息框选择“没点错”后的情况）
const messagebox19 = () => {
  // console.log('我调用了19号函数')
  return messagebox3()
};

// 第二十个消息框函数（对应用户关闭的时候）
// const messagebox20 = () => {
//   return ElMessageBox.confirm('能不能点点看看', '能不能点点看看', {
//     confirmButtonText: '能',
//     cancelButtonText: '不能'
//   });
// };


// ai代码

const jumpToPage = () => {
  router.push('/nqtajdtzqaxmfsxmfs')
};
const startMessage = () => {
  messagebox1()
  .then(() => {
      // console.log('第一个正确');
      return handleMessagebox2()
    })
  .catch((error) => {
      // console.log('第一个错误');
      return handleMessagebox3();
    });
};

const handleMessagebox2 = () => {
  return messagebox2()
  .then(() => {
      // console.log('第一个正确');
      return handleMessagebox4()
    })
  。catch((error) => {
      // console.log('用户在第二个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox5();
    });
};

const handleMessagebox3 = () => {
  return messagebox3()
  。then(() => {
    // console.log('第三个正确');
    return handleMessagebox2()
    // return handleMessagebox12()
    })
  。catch((error) => {
      // console.log('用户在第三个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox13();
    });
};

const handleMessagebox4 = () => {
  return messagebox4()
  。then(() => {
      // console.log('第四个正确');
      return handleMessagebox6()
    })
  。catch((error) => {
      // console.log('用户在第四个消息框点击了取消按钮，错误信息:', error);
      // return handleMessagebox7();
      return handleMessagebox3();
    });
};

const handleMessagebox5 = () => {
  return messagebox5()
  。then(() => {
      // console.log('第五个正确');
      return handleMessagebox18()
    })
  。catch((error) => {
      // console.log('用户在第五个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox3();
    });
};

const handleMessagebox6 = () => {
  return messagebox6()
  。then(() => {
      // console.log('第六个正确');
      return handleMessagebox8()
    })
  。catch((error) => {
      // console.log('用户在第六个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox9();
    });
};

const handleMessagebox7 = () => {
  return messagebox7()
  。then(() => {
      // console.log('用户确认了第七个消息框操作，后续可添加更多逻辑');
      
    })
  。catch((error) => {
      // console.log('用户在第七个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox3()
    });
};

const handleMessagebox8 = () => {
  return messagebox8()
  。then(() => {
      // console.log('第八个正确');
      return handleMessagebox10()
    })
  。catch((error) => {
      // console.log('用户在第八个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox11();
    });
};

const handleMessagebox9 = () => {
  return messagebox9()
  。then(() => {
      // console.log('用户确认了第九个消息框操作，后续可添加更多逻辑');
      // router.push('/nqtajdtzqaxmfsxmfs')
    })
  。catch((error) => {
      // console.log('用户在第九个消息框点击了取消按钮，错误信息:', error);
    });
};

const handleMessagebox10 = () => {
  return messagebox10()
  .then(() =>  {
      // console.log('用户确认了第十个消息框操作，后续可添加更多逻辑');
      jumpToPage()
      // router.push('/nqtajdtzqaxmfsxmfs')
      ElMessage.success('我去买票了');
    })
  .catch((error) => {
      // console.log('用户在第十个消息框点击了取消按钮，错误信息:', error);
    });
};

const handleMessagebox11 = () => {
  return messagebox11()
  .then(() => {
      // console.log('用户确认了第十一个消息框操作，后续可添加更多逻辑');
    })
  .catch((error) => {
      // console.log('用户在第十一个消息框点击了取消按钮，错误信息:', error);
    });
};

const handleMessagebox12 = () => {
  return messagebox12()
  .then(() => {
      // console.log('第十二个正确');
      return handleMessagebox2()
    })
  .catch((error) => {
      // console.log('用户在第十二个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox2();
    });
};

const handleMessagebox13 = () => {
  return messagebox13()
  .then(() => {
      // console.log('第十三个正确');
      return handleMessagebox2()
    })
  .catch((error) => {
      // console.log('用户在第十三个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox15();
    });
};

const handleMessagebox14 = () => {
  return messagebox14()
  .then(() => {
    // console.log('第十四个正确');
    return handleMessagebox2()
    })
  .catch((error) => {
      // console.log('用户在第十四个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox2();
    });
};

const handleMessagebox15 = () => {
  return messagebox15()
  .then(() => {
    // console.log('第十五个正确');
    return handleMessagebox2()})
  .catch((error) => {
      // console.log('用户在第十五个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox17();
    });
};

const handleMessagebox16 = () => {
  return messagebox16()
  .then(() => {
    // console.log('第十六个正确');
    return handleMessagebox2()})
  .catch((error) => {
      // console.log('用户在第十六个消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox2();
    });
};

const handleMessagebox17 = () => {
  return messagebox17()
  .then(() => {
      // console.log('用户确认了第十七個消息框操作，后续可添加更多逻辑');
    })
  .catch((error) => {
      // console.log('用户在第十七個消息框点击了取消按钮，错误信息:', error);
    });
};

const handleMessagebox18 = () => {
  return messagebox18()
  .then(() => {
      // console.log('用户确认了第十八個消息框操作，后续可添加更多逻辑');
      // 逻辑未添加跳messsage6
      return handleMessagebox6();
    })
  .catch((error) => {
      // console.log('用户在第十八個消息框点击了取消按钮，错误信息:', error);
      return handleMessagebox3()
    });
};

// const handleMessagebox19 = () => {
//   return messagebox19()
//   .then(() => {
//       console.log('用户确认了第十九個消息框操作，后续可添加更多逻辑');
//       return handleMessagebox3();
//     })
//   .catch((error) => {
//       console.log('用户在第十九個消息框点击了取消按钮，错误信息:', error);
//       return handleMessagebox3()
//     });
// };


</script>

<template>
  <!-- <el-button type="primary" size="large"  @click="openMessageBox">彩蛋</el-button>
   -->
   <el-button type="primary" size="large" @click="startMessage">彩蛋</el-button>
   <!-- <div>测试</div> -->
   <!-- 哪位仁兄看见这行注释，如果有想法可以推荐一下这段提示框咋写或者给个小插件用用也行，快给我写吐了-我都整出来思维导图照着写，还是没写好，mmp，给我自己都快绕晕了，就这一个小小弹窗我写了将近400行，我的联系邮箱在/vidoo页的右下角，或者评论留个TG我加一下 -->
</template>

<style lang="less" scoped>

</style>
